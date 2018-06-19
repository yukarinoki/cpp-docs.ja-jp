---
title: '方法: ADO.NET の SAFEARRAY をマーシャ リング (C + + CLI) |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ddd6250fac293fef58ccc21894661ddf32e3fa61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137420"
---
# <a name="how-to-marshal-a-safearray-for-adonet-ccli"></a>方法: ADO.NET の SAFEARRAY をマーシャリングする (C++/CLI)
ネイティブを追加する方法を示します`SAFEARRAY`データベースからネイティブへのマネージ配列にマーシャ リングする方法、およびデータベースに`SAFEARRAY`です。  
  
## <a name="example"></a>例  
 この例では、クラス DatabaseClass が作成される、ADO.NET と対話する<xref:System.Data.DataTable>オブジェクト。 このクラスは、ネイティブ C++ `class` (に比べて、`ref class`または`value class`)。 これは、機能は、ネイティブ コードからこのクラスを使用して、マネージ型をネイティブ コードで使用することはできませんので必要です。 このクラスはによって示される、CLR をターゲットにコンパイルされます、`#pragma managed`クラス宣言の前のディレクティブ。 このディレクティブの詳細については、次を参照してください。[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)です。  
  
 DatabaseClass クラスのプライベート メンバーに注意してください:`gcroot<DataTable ^> table`です。 ネイティブ型はマネージ型を含めることはできませんので、`gcroot`キーワードが必要です。 詳細については`gcroot`を参照してください[する方法: ネイティブ型内のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)です。  
  
 この例では、コードの残りの部分は、ネイティブの C++ コードで示される、`#pragma unmanaged`ディレクティブの前`main`です。 この例ではお DatabaseClass の新しいインスタンスを作成する、テーブルを作成し、テーブル内のいくつかの行を設定するには、そのメソッドを呼び出します。 ネイティブに注意してください`SAFEARRAY`ArrayIntsCol データベース列の値として渡される型です。 DatabaseClass、内部これら`SAFEARRAY`型はマーシャ リングの機能を使用してマネージ オブジェクトをマーシャ リング、<xref:System.Runtime.InteropServices?displayProperty=fullName>名前空間。 メソッドでは具体的には、<xref:System.Runtime.InteropServices.Marshal.Copy%2A>をマーシャ リングするために使用、`SAFEARRAY`整数、およびメソッドのマネージ配列<xref:System.Runtime.InteropServices.Marshal.Copy%2A>に整数のマネージ配列にマーシャ リングするために使用、`SAFEARRAY`です。  
  
```  
// adonet_marshal_safearray.cpp  
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
  
    void AddRow(SAFEARRAY *arrayIntsColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        int len = arrayIntsColValue->rgsabound[0].cElements;  
        array<int> ^arr = gcnew array<int>(len);  
  
        int *pData;  
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);  
        Marshal::Copy(IntPtr(pData), arr, 0, len);  
        SafeArrayUnaccessData(arrayIntsColValue);  
  
        row["ArrayIntsCol"] = arr;  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",  
            Type::GetType("System.Int32[]"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,  
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
            // Marshal each column value from a managed array  
            // of Int32s to a SAFEARRAY of type VT_I4.  
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);  
            int *pData;  
            SafeArrayAccessData(values[i], (void **)&pData);  
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,  
                IntPtr(pData), 10);  
            SafeArrayUnaccessData(values[i]);  
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
  
    // Create a standard array.  
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
    // Create a SAFEARRAY.  
    SAFEARRAY *psa;  
    psa = SafeArrayCreateVector(VT_I4, 0, 10);  
  
    // Copy the data from the original array to the SAFEARRAY.  
    int *pData;  
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);  
    memcpy(pData, &originalArray, 40);  
    SafeArrayUnaccessData(psa);  
    db->AddRow(psa);  
  
    // Now retrieve the rows and display their contents.  
    SAFEARRAY *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ArrayIntsCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        int *pData;  
        SafeArrayAccessData(values[i], (void **)&pData);  
        for (int j = 0; j < 10; j++)  
        {  
            cout << pData[j] << " ";  
        }  
        cout << endl;  
        SafeArrayUnaccessData(values[i]);  
  
        // Deallocate the memory allocated using  
        // SafeArrayCreateVector.  
        SafeArrayDestroy(values[i]);  
    }  
  
    SafeArrayDestroy(psa);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
-   コマンドラインからコードをコンパイルするには、コード サンプルを adonet_marshal_safearray.cpp をという名前のファイルで保存し、次のステートメントを入力します。  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 ADO.NET に関連するセキュリティ問題については、次を参照してください。 [ADO.NET アプリケーションのセキュリティで保護する](/dotnet/framework/data/adonet/securing-ado-net-applications)です。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET を使用してデータ アクセス (C + + CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [相互運用性](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)