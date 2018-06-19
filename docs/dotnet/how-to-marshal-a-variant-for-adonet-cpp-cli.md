---
title: '方法: ADO.NET の VARIANT をマーシャ リング (C + + CLI) |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b442dcce2cdde28de8db1610971dd72dba84ab52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134440"
---
# <a name="how-to-marshal-a-variant-for-adonet-ccli"></a>方法: ADO.NET の VARIANT をマーシャリングする (C++/CLI)
ネイティブを追加する方法を示します`VARIANT`をマーシャ リングする方法、およびデータベースを<xref:System.Object?displayProperty=fullName>をネイティブ データベースから`VARIANT`です。  
  
## <a name="example"></a>例  
 この例では、クラス DatabaseClass が作成される、ADO.NET と対話する<xref:System.Data.DataTable>オブジェクト。 このクラスは、ネイティブ C++ `class` (に比べて、`ref class`または`value class`)。 これは、機能は、ネイティブ コードからこのクラスを使用して、マネージ型をネイティブ コードで使用することはできませんので必要です。 このクラスはによって示される、CLR をターゲットにコンパイルされます、`#pragma managed`クラス宣言の前のディレクティブ。 このディレクティブの詳細については、次を参照してください。[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)です。  
  
 DatabaseClass クラスのプライベート メンバーに注意してください:`gcroot<DataTable ^> table`です。 ネイティブ型はマネージ型を含めることはできませんので、`gcroot`キーワードが必要です。 詳細については`gcroot`を参照してください[する方法: ネイティブ型内のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)です。  
  
 この例では、コードの残りの部分は、ネイティブの C++ コードで示される、`#pragma unmanaged`ディレクティブの前`main`です。 この例ではお DatabaseClass の新しいインスタンスを作成する、テーブルを作成し、テーブル内のいくつかの行を設定するには、そのメソッドを呼び出します。 ネイティブに注意してください`VARIANT`ObjectCol データベース列の値として渡される型です。 DatabaseClass、内部これら`VARIANT`型はマーシャ リングの機能を使用してマネージ オブジェクトをマーシャ リング、<xref:System.Runtime.InteropServices?displayProperty=fullName>名前空間。 メソッドでは具体的には、<xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A>をマーシャ リングするために使用、`VARIANT`を<xref:System.Object>、およびメソッド<xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A>をマーシャ リングするために使用、<xref:System.Object>を`VARIANT`です。  
  
```  
// adonet_marshal_variant.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
ObjectCol: This is a BSTR in a VARIANT.  
ObjectCol: 42  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
-   コマンドラインからコードをコンパイルするには、コード サンプルを adonet_marshal_variant.cpp をという名前のファイルで保存し、次のステートメントを入力します。  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 ADO.NET に関連するセキュリティ問題については、次を参照してください。 [ADO.NET アプリケーションのセキュリティで保護する](/dotnet/framework/data/adonet/securing-ado-net-applications)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET を使用してデータ アクセス (C + + CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [相互運用性](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)