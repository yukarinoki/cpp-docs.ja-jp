---
description: '詳細情報: ADO.NET を使用したデータアクセス (C++/CLI)'
title: ADO.NET によるデータ アクセス (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
- native strings [C++]
- ADO.NET [C++], marshaling ANSI strings
- strings [C++], ADO.NET
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
ms.openlocfilehash: 93af8a8a2dc4ebc8d9fe6073b9f3a70f4868bee8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124268"
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET によるデータ アクセス (C++/CLI)

ADO.NET は、データアクセス用の .NET Framework API であり、以前のデータアクセスソリューションによって、機能が優れており、使いやすさが向上しています。 このセクションでは、ネイティブ型のマーシャリングなど、Visual C++ のユーザーに固有の ADO.NET 関連の問題について説明します。

ADO.NET は、共通言語ランタイム (CLR) で実行されます。 そのため、ADO.NET と対話するアプリケーションでも、CLR を対象とする必要があります。 ただし、これは、ネイティブアプリケーションが ADO.NET を使用できないことを意味するわけではありません。 これらの例では、ネイティブコードから ADO.NET データベースを操作する方法を示します。

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a> ADO.NET の ANSI 文字列のマーシャリング

ネイティブ文字列 () をデータベースに追加する方法 `char *` と、を <xref:System.String?displayProperty=fullName> データベースからネイティブ文字列にマーシャリングする方法について説明します。

### <a name="example"></a>例

この例では、ADO.NET オブジェクトと対話するためにクラス DatabaseClass が作成され <xref:System.Data.DataTable> ます。 このクラスは、ネイティブ C++ (またはと比較) であることに注意し **`class`** て **`ref class`** **`value class`** ください。 これは、ネイティブコードからこのクラスを使用する必要があり、マネージ型をネイティブコードで使用できないために必要です。 このクラスは、クラス宣言の前にあるディレクティブによって示されているように、CLR を対象としてコンパイルされ `#pragma managed` ます。 このディレクティブの詳細については、「 [マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

DatabaseClass クラスのプライベートメンバーであるを確認 `gcroot<DataTable ^> table` します。 ネイティブ型にはマネージ型を含めることができないため、 `gcroot` キーワードが必要です。 の詳細につい `gcroot` ては、「 [方法: ネイティブ型のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)する」を参照してください。

この例の残りのコードは、前のディレクティブで示されているように、ネイティブ C++ コードです `#pragma unmanaged` `main` 。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルにいくつかの行を設定します。 ネイティブ C++ 文字列は、データベース列 StringCol の値として渡されることに注意してください。 DatabaseClass の内部では、これらの文字列は、名前空間にあるマーシャリング機能を使用して、マネージ文字列にマーシャリングされ <xref:System.Runtime.InteropServices?displayProperty=fullName> ます。 具体的には、メソッドを使用してを <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> にマーシャリングし、メソッドを使用してを `char *` <xref:System.String> <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> にマーシャリングし <xref:System.String> `char *` ます。

> [!NOTE]
> によって割り当てられたメモリを <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 解放するに <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> は、またはを呼び出し `GlobalFree` ます。

```cpp
// adonet_marshal_string_native.cpp
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

    void AddRow(char *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringAnsi(
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

    int GetValuesForColumn(char *dataColumn, char **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringAnsi(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a char *.
            values[i] = (char *)Marshal::StringToHGlobalAnsi(
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
    db->AddRow("This is string 1.");
    db->AddRow("This is string 2.");

    // Now retrieve the rows and display their contents.
    char *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        "StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        cout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalAnsi.
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

### <a name="compiling-the-code"></a>コードのコンパイル

- コマンドラインからコードをコンパイルするには、コード例を adonet_marshal_string_native .cpp という名前のファイルに保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a> ADO.NET の BSTR 文字列のマーシャリング

データベースに COM 文字列 () を追加する方法と、を `BSTR` データベースからにマーシャリングする方法を示し <xref:System.String?displayProperty=fullName> `BSTR` ます。

### <a name="example"></a>例

この例では、ADO.NET オブジェクトと対話するためにクラス DatabaseClass が作成され <xref:System.Data.DataTable> ます。 このクラスは、ネイティブ C++ (またはと比較) であることに注意し **`class`** て **`ref class`** **`value class`** ください。 これは、ネイティブコードからこのクラスを使用する必要があり、マネージ型をネイティブコードで使用できないために必要です。 このクラスは、クラス宣言の前にあるディレクティブによって示されているように、CLR を対象としてコンパイルされ `#pragma managed` ます。 このディレクティブの詳細については、「 [マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

DatabaseClass クラスのプライベートメンバーであるを確認 `gcroot<DataTable ^> table` します。 ネイティブ型にはマネージ型を含めることができないため、 `gcroot` キーワードが必要です。 の詳細につい `gcroot` ては、「 [方法: ネイティブ型のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)する」を参照してください。

この例の残りのコードは、前のディレクティブで示されているように、ネイティブ C++ コードです `#pragma unmanaged` `main` 。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルにいくつかの行を設定します。 COM 文字列は、データベース列 StringCol の値として渡されることに注意してください。 DatabaseClass の内部では、これらの文字列は、名前空間にあるマーシャリング機能を使用して、マネージ文字列にマーシャリングされ <xref:System.Runtime.InteropServices?displayProperty=fullName> ます。 具体的には、メソッドを使用してを <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> にマーシャリングし、メソッドを使用してを `BSTR` <xref:System.String> <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> にマーシャリングし <xref:System.String> `BSTR` ます。

> [!NOTE]
> によって割り当てられたメモリを <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> 解放するに <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> は、またはを呼び出し `SysFreeString` ます。

``` cpp
// adonet_marshal_string_bstr.cpp
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

    void AddRow(BSTR stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringBSTR(
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

    int GetValuesForColumn(BSTR dataColumn, BSTR *values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringBSTR(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a BSTR.
            values[i] = (BSTR)Marshal::StringToBSTR(
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

    BSTR str1 = SysAllocString(L"This is string 1.");
    db->AddRow(str1);

    BSTR str2 = SysAllocString(L"This is string 2.");
    db->AddRow(str2);

    // Now retrieve the rows and display their contents.
    BSTR values[MAXCOLS];
    BSTR str3 = SysAllocString(L"StringCol");
    int len = db->GetValuesForColumn(
        str3, values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        wcout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToBSTR.
        SysFreeString(values[i]);
    }

    SysFreeString(str1);
    SysFreeString(str2);
    SysFreeString(str3);
    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>コードのコンパイル

- コマンドラインからコードをコンパイルするには、コード例を adonet_marshal_string_native .cpp という名前のファイルに保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a> ADO.NET の Unicode 文字列のマーシャリング

ネイティブ Unicode 文字列 () をデータベースに追加する方法 `wchar_t *` と、を <xref:System.String?displayProperty=fullName> データベースからネイティブ unicode 文字列にマーシャリングする方法について説明します。

### <a name="example"></a>例

この例では、ADO.NET オブジェクトと対話するためにクラス DatabaseClass が作成され <xref:System.Data.DataTable> ます。 このクラスは、ネイティブ C++ (またはと比較) であることに注意し **`class`** て **`ref class`** **`value class`** ください。 これは、ネイティブコードからこのクラスを使用する必要があり、マネージ型をネイティブコードで使用できないために必要です。 このクラスは、クラス宣言の前にあるディレクティブによって示されているように、CLR を対象としてコンパイルされ `#pragma managed` ます。 このディレクティブの詳細については、「 [マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

DatabaseClass クラスのプライベートメンバーであるを確認 `gcroot<DataTable ^> table` します。 ネイティブ型にはマネージ型を含めることができないため、 `gcroot` キーワードが必要です。 の詳細につい `gcroot` ては、「 [方法: ネイティブ型のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)する」を参照してください。

この例の残りのコードは、前のディレクティブで示されているように、ネイティブ C++ コードです `#pragma unmanaged` `main` 。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルにいくつかの行を設定します。 Unicode C++ 文字列は、データベース列 StringCol の値として渡されることに注意してください。 DatabaseClass の内部では、これらの文字列は、名前空間にあるマーシャリング機能を使用して、マネージ文字列にマーシャリングされ <xref:System.Runtime.InteropServices?displayProperty=fullName> ます。 具体的には、メソッドを使用してを <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> にマーシャリングし、メソッドを使用してを `wchar_t *` <xref:System.String> <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> にマーシャリングし <xref:System.String> `wchar_t *` ます。

> [!NOTE]
> によって割り当てられたメモリを <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> 解放するに <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> は、またはを呼び出し `GlobalFree` ます。

```cpp
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

### <a name="compiling-the-code"></a>コードのコンパイル

- コマンドラインからコードをコンパイルするには、コード例を adonet_marshal_string_wide .cpp という名前のファイルに保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a> ADO.NET の VARIANT をマーシャリングする

データベースにネイティブを追加する方法と、を `VARIANT` データベースからネイティブにマーシャリングする方法について説明し <xref:System.Object?displayProperty=fullName> `VARIANT` ます。

### <a name="example"></a>例

この例では、ADO.NET オブジェクトと対話するためにクラス DatabaseClass が作成され <xref:System.Data.DataTable> ます。 このクラスは、ネイティブ C++ (またはと比較) であることに注意し **`class`** て **`ref class`** **`value class`** ください。 これは、ネイティブコードからこのクラスを使用する必要があり、マネージ型をネイティブコードで使用できないために必要です。 このクラスは、クラス宣言の前にあるディレクティブによって示されているように、CLR を対象としてコンパイルされ `#pragma managed` ます。 このディレクティブの詳細については、「 [マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

DatabaseClass クラスのプライベートメンバーであるを確認 `gcroot<DataTable ^> table` します。 ネイティブ型にはマネージ型を含めることができないため、 `gcroot` キーワードが必要です。 の詳細につい `gcroot` ては、「 [方法: ネイティブ型のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)する」を参照してください。

この例の残りのコードは、前のディレクティブで示されているように、ネイティブ C++ コードです `#pragma unmanaged` `main` 。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルにいくつかの行を設定します。 ネイティブ `VARIANT` 型は、データベース列 ObjectCol の値として渡されることに注意してください。 DatabaseClass の内部では、これらの `VARIANT` 型は、名前空間にあるマーシャリング機能を使用して、マネージオブジェクトにマーシャリングされ <xref:System.Runtime.InteropServices?displayProperty=fullName> ます。 具体的には、メソッドを使用してをにマーシャリングし、メソッドを使用してをに <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> `VARIANT` マーシャリングし <xref:System.Object> <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> <xref:System.Object> `VARIANT` ます。

```cpp
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

### <a name="compiling-the-code"></a>コードのコンパイル

- コマンドラインからコードをコンパイルするには、コード例を adonet_marshal_variant .cpp という名前のファイルに保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a> ADO.NET の SAFEARRAY をマーシャリングする

データベースにネイティブを追加する方法 `SAFEARRAY` と、マネージ配列をデータベースからネイティブにマーシャリングする方法について説明し `SAFEARRAY` ます。

### <a name="example"></a>例

この例では、ADO.NET オブジェクトと対話するためにクラス DatabaseClass が作成され <xref:System.Data.DataTable> ます。 このクラスは、ネイティブ C++ (またはと比較) であることに注意し **`class`** て **`ref class`** **`value class`** ください。 これは、ネイティブコードからこのクラスを使用する必要があり、マネージ型をネイティブコードで使用できないために必要です。 このクラスは、クラス宣言の前にあるディレクティブによって示されているように、CLR を対象としてコンパイルされ `#pragma managed` ます。 このディレクティブの詳細については、「 [マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

DatabaseClass クラスのプライベートメンバーであるを確認 `gcroot<DataTable ^> table` します。 ネイティブ型にはマネージ型を含めることができないため、 `gcroot` キーワードが必要です。 の詳細につい `gcroot` ては、「 [方法: ネイティブ型のハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)する」を参照してください。

この例の残りのコードは、前のディレクティブで示されているように、ネイティブ C++ コードです `#pragma unmanaged` `main` 。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルにいくつかの行を設定します。 ネイティブ `SAFEARRAY` 型は、データベース列 ArrayIntsCol の値として渡されることに注意してください。 DatabaseClass の内部では、これらの `SAFEARRAY` 型は、名前空間にあるマーシャリング機能を使用して、マネージオブジェクトにマーシャリングされ <xref:System.Runtime.InteropServices?displayProperty=fullName> ます。 具体的には、メソッドは、 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> を整数のマネージ配列にマーシャリングするために使用され `SAFEARRAY` ます。また、メソッドを使用して、 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 整数のマネージ配列をにマーシャリングし `SAFEARRAY` ます。

```cpp
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

### <a name="compiling-the-code"></a>コードのコンパイル

- コマンドラインからコードをコンパイルするには、コード例を adonet_marshal_safearray .cpp という名前のファイルに保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework セキュリティ

ADO.NET に関連するセキュリティの問題の詳細については、「 [ADO.NET アプリケーション](/dotnet/framework/data/adonet/securing-ado-net-applications)のセキュリティ保護」を参照してください。

## <a name="related-sections"></a>関連項目

|Section|説明|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|.NET プログラマにデータアクセスサービスを公開するクラスのセット ADO.NET の概要について説明します。|

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[相互運用性](/dotnet/framework/interop/index)
