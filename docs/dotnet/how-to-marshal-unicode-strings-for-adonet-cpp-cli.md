---
title: '方法: ADO.NET の Unicode 文字列をマーシャ リング (C + + CLI) |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
ms.assetid: 1da090ff-6b53-40be-841f-dc79dfe8ba10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 15cf9e9806c0820ea5a410a93419016c2f678c65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137375"
---
# <a name="how-to-marshal-unicode-strings-for-adonet-ccli"></a>方法: ADO.NET の Unicode 文字列をマーシャリングする (C++/CLI)
ネイティブの Unicode 文字列を追加する方法を示します (`wchar_t *`) をマーシャ リングする方法、およびデータベースを<xref:System.String?displayProperty=fullName>ネイティブの Unicode 文字列をデータベースからです。  
  
## <a name="example"></a>例  
 この例では、クラス DatabaseClass が作成される、ADO.NET と対話する<xref:System.Data.DataTable>オブジェクト。 このクラスは、ネイティブ C++ `class` (に比べて、`ref class`または`value class`)。 これは、機能は、ネイティブ コードからこのクラスを使用して、マネージ型をネイティブ コードで使用することはできませんので必要です。 このクラスはによって示される、CLR をターゲットにコンパイルされます、`#pragma managed`クラス宣言の前のディレクティブ。 このディレクティブの詳細については、次を参照してください。[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)です。  
  
 DatabaseClass クラスのプライベート メンバーに注意してください:`gcroot<DataTable ^> table`です。 ネイティブ型はマネージ型を含めることはできませんので、`gcroot`キーワードが必要です。 詳細については`gcroot`を参照してください[する方法: ネイティブ型内のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)です。  
  
 この例では、コードの残りの部分は、ネイティブの C++ コードで示される、`#pragma unmanaged`ディレクティブの前`main`です。 この例ではお DatabaseClass の新しいインスタンスを作成する、テーブルを作成し、テーブル内のいくつかの行を設定するには、そのメソッドを呼び出します。 StringCol データベース列の値として C++ の Unicode 文字列が渡されていることに注意してください。 内部 DatabaseClass、これらの文字列をマーシャ リングの機能を使用して管理対象の文字列にマーシャ リングします。、<xref:System.Runtime.InteropServices?displayProperty=fullName>名前空間。 メソッドでは具体的には、<xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A>をマーシャ リングするために使用、`wchar_t *`を<xref:System.String>、およびメソッド<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A>をマーシャ リングするために使用、<xref:System.String>を`wchar_t *`です。  
  
> [!NOTE]
>  によって割り当てられたメモリ<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A>を呼び出して、割り当てを解除する必要があります<xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A>または`GlobalFree`です。  
  
```  
// adonet_marshal_string_wide.cpp  
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
  
    void AddRow(wchar_t *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringUni(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,  
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
            // Marshal each column value from a managed string  
            // to a wchar_t *.  
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(  
                (String ^)rows[i][columnStr]).ToPointer();  
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
    db->AddRow(L"This is string 1.");  
    db->AddRow(L"This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    wchar_t *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalUni.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
-   コマンドラインからコードをコンパイルするには、コード サンプルを adonet_marshal_string_wide.cpp をという名前のファイルで保存し、次のステートメントを入力します。  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 ADO.NET に関連するセキュリティ問題については、次を参照してください。 [ADO.NET アプリケーションのセキュリティで保護する](/dotnet/framework/data/adonet/securing-ado-net-applications)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET を使用してデータ アクセス (C + + CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [相互運用性](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)