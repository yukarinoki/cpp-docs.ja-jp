---
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
ms.openlocfilehash: 35633449c4c01f5c103dcd54b81c0d6aa7c08cdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364409"
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET によるデータ アクセス (C++/CLI)

ADO.NETは、データ アクセス用の .NET Framework API であり、以前のデータ アクセス ソリューションと比類のない機能と使いやすさを提供します。 ここでは、ネイティブ型のマーシャリングなど、Visual C++ ユーザーに固有のADO.NETに関する問題について説明します。

ADO.NET共通言語ランタイム (CLR) の下で実行されます。 したがって、ADO.NETと対話するアプリケーションも、CLR を対象にする必要があります。 ただし、ネイティブ アプリケーションがADO.NETを使用できないという意味ではありません。 これらの例では、ネイティブ コードからADO.NET データベースと対話する方法を示します。

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a>ADO.NET用の ANSI 文字列のマーシャリング

ネイティブ文字列 ( )`char *`をデータベースに追加する方法と、データベース<xref:System.String?displayProperty=fullName>からネイティブ文字列にマーシャリングする方法について説明します。

### <a name="example"></a>例

この例では、ADO.NET<xref:System.Data.DataTable>オブジェクトと対話するためにクラス DatabaseClass が作成されます。 このクラスはネイティブ C++`class`です (a`ref class`または`value class`と比較)。 ネイティブ コードからこのクラスを使用する必要があり、ネイティブ コードでマネージ型を使用できないため、この方法は必要です。 このクラスは、クラス宣言の前にディレクティブが示すように、CLR`#pragma managed`を対象にコンパイルされます。 このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

クラスのプライベート メンバに注意してください。 `gcroot<DataTable ^> table` ネイティブ型にマネージ型を含めることはできませんの`gcroot`で、キーワードが必要です。 の詳細については、「[方法 : ネイティブ型でハンドルを宣言する 」を参照してください。](../dotnet/how-to-declare-handles-in-native-types.md) `gcroot`

この例のコードの残りの部分は、前の`#pragma unmanaged`ディレクティブで示されているように、ネイティブ C++`main`コードです。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルの行をいくつか設定します。 ネイティブ C++ 文字列は、データベース列 StringCol の値として渡されることに注意してください。 DatabaseClass 内では、これらの文字列は、名前空間にあるマーシャリング機能を使用してマネージ文字列に<xref:System.Runtime.InteropServices?displayProperty=fullName>マーシャリングされます。 具体的には、<xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A>`char *`メソッドを使用して を<xref:System.String>a にマーシャリング<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>し、メソッドを使用<xref:System.String>して`char *`を a にマーシャリングします。

> [!NOTE]
> 割り当てられたメモリ<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>は、 または<xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A>`GlobalFree`を呼び出すことによって割り当てを解除する必要があります。

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

- コマンド ラインからコードをコンパイルするには、adonet_marshal_string_native.cpp という名前のファイルにコード例を保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a>ADO.NETの BSTR 文字列をマーシャリングする

COM 文字列 ( )`BSTR`をデータベースに追加する方法と、 データベース<xref:System.String?displayProperty=fullName>から を に`BSTR`マーシャリングする方法について説明します。

### <a name="example"></a>例

この例では、ADO.NET<xref:System.Data.DataTable>オブジェクトと対話するためにクラス DatabaseClass が作成されます。 このクラスはネイティブ C++`class`です (a`ref class`または`value class`と比較)。 ネイティブ コードからこのクラスを使用する必要があり、ネイティブ コードでマネージ型を使用できないため、この方法は必要です。 このクラスは、クラス宣言の前にディレクティブが示すように、CLR`#pragma managed`を対象にコンパイルされます。 このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

クラスのプライベート メンバに注意してください。 `gcroot<DataTable ^> table` ネイティブ型にマネージ型を含めることはできませんの`gcroot`で、キーワードが必要です。 の詳細については、「[方法 : ネイティブ型でハンドルを宣言する 」を参照してください。](../dotnet/how-to-declare-handles-in-native-types.md) `gcroot`

この例のコードの残りの部分は、前の`#pragma unmanaged`ディレクティブで示されているように、ネイティブ C++`main`コードです。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルの行をいくつか設定します。 COM 文字列は、データベース列 StringCol の値として渡されることに注意してください。 DatabaseClass 内では、これらの文字列は、名前空間にあるマーシャリング機能を使用してマネージ文字列に<xref:System.Runtime.InteropServices?displayProperty=fullName>マーシャリングされます。 具体的には、<xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A>`BSTR`メソッドを使用して を<xref:System.String>a にマーシャリング<xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A>し、メソッドを使用<xref:System.String>して`BSTR`を a にマーシャリングします。

> [!NOTE]
> 割り当てられたメモリ<xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A>は、 または<xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A>`SysFreeString`を呼び出すことによって割り当てを解除する必要があります。

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

- コマンド ラインからコードをコンパイルするには、adonet_marshal_string_native.cpp という名前のファイルにコード例を保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a>ADO.NET用のユニコード文字列のマーシャリング

ネイティブ Unicode 文字列 ( )`wchar_t *`をデータベースに追加する方法と、データベース<xref:System.String?displayProperty=fullName>からネイティブの Unicode 文字列にマーシャリングする方法について説明します。

### <a name="example"></a>例

この例では、ADO.NET<xref:System.Data.DataTable>オブジェクトと対話するためにクラス DatabaseClass が作成されます。 このクラスはネイティブ C++`class`です (a`ref class`または`value class`と比較)。 ネイティブ コードからこのクラスを使用する必要があり、ネイティブ コードでマネージ型を使用できないため、この方法は必要です。 このクラスは、クラス宣言の前にディレクティブが示すように、CLR`#pragma managed`を対象にコンパイルされます。 このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

クラスのプライベート メンバに注意してください。 `gcroot<DataTable ^> table` ネイティブ型にマネージ型を含めることはできませんの`gcroot`で、キーワードが必要です。 の詳細については、「[方法 : ネイティブ型でハンドルを宣言する 」を参照してください。](../dotnet/how-to-declare-handles-in-native-types.md) `gcroot`

この例のコードの残りの部分は、前の`#pragma unmanaged`ディレクティブで示されているように、ネイティブ C++`main`コードです。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルの行をいくつか設定します。 Unicode C++ 文字列は、データベース列 StringCol の値として渡されることに注意してください。 DatabaseClass 内では、これらの文字列は、名前空間にあるマーシャリング機能を使用してマネージ文字列に<xref:System.Runtime.InteropServices?displayProperty=fullName>マーシャリングされます。 具体的には、<xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A>`wchar_t *`メソッドを使用して を<xref:System.String>a にマーシャリング<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A>し、メソッドを使用<xref:System.String>して`wchar_t *`を a にマーシャリングします。

> [!NOTE]
> 割り当てられたメモリ<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A>は、 または<xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A>`GlobalFree`を呼び出すことによって割り当てを解除する必要があります。

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

- コマンド ラインからコードをコンパイルするには、adonet_marshal_string_wide.cpp という名前のファイルにコード例を保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a>ADO.NETのバリアントをマーシャリングする

データベースにネイティブを追加する方法`VARIANT`と、 データベース<xref:System.Object?displayProperty=fullName>からネイティブ`VARIANT`にマーシャリングする方法を示します。

### <a name="example"></a>例

この例では、ADO.NET<xref:System.Data.DataTable>オブジェクトと対話するためにクラス DatabaseClass が作成されます。 このクラスはネイティブ C++`class`です (a`ref class`または`value class`と比較)。 ネイティブ コードからこのクラスを使用する必要があり、ネイティブ コードでマネージ型を使用できないため、この方法は必要です。 このクラスは、クラス宣言の前にディレクティブが示すように、CLR`#pragma managed`を対象にコンパイルされます。 このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

クラスのプライベート メンバに注意してください。 `gcroot<DataTable ^> table` ネイティブ型にマネージ型を含めることはできませんの`gcroot`で、キーワードが必要です。 の詳細については、「[方法 : ネイティブ型でハンドルを宣言する 」を参照してください。](../dotnet/how-to-declare-handles-in-native-types.md) `gcroot`

この例のコードの残りの部分は、前の`#pragma unmanaged`ディレクティブで示されているように、ネイティブ C++`main`コードです。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルの行をいくつか設定します。 ネイティブ`VARIANT`型は、データベース列 ObjectCol の値として渡されることに注意してください。 DatabaseClass 内では`VARIANT`、これらの型は、名前空間にあるマーシャリング機能を使用してマネージ オブジェクト<xref:System.Runtime.InteropServices?displayProperty=fullName>にマーシャリングされます。 具体的には、<xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A>メソッドを使用`VARIANT`して を<xref:System.Object>にマーシャリングし、<xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A>にマーシャリング<xref:System.Object>します。 `VARIANT`

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

- コマンド ラインからコードをコンパイルするには、adonet_marshal_variant.cpp という名前のファイルにコード例を保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a>ADO.NETのためのセーフアレイをマーシャリングする

データベースにネイティブ`SAFEARRAY`を追加する方法と、マネージ配列をデータベースからネイティブ`SAFEARRAY`にマーシャリングする方法を示します。

### <a name="example"></a>例

この例では、ADO.NET<xref:System.Data.DataTable>オブジェクトと対話するためにクラス DatabaseClass が作成されます。 このクラスはネイティブ C++`class`です (a`ref class`または`value class`と比較)。 ネイティブ コードからこのクラスを使用する必要があり、ネイティブ コードでマネージ型を使用できないため、この方法は必要です。 このクラスは、クラス宣言の前にディレクティブが示すように、CLR`#pragma managed`を対象にコンパイルされます。 このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。

クラスのプライベート メンバに注意してください。 `gcroot<DataTable ^> table` ネイティブ型にマネージ型を含めることはできませんの`gcroot`で、キーワードが必要です。 の詳細については、「[方法 : ネイティブ型でハンドルを宣言する 」を参照してください。](../dotnet/how-to-declare-handles-in-native-types.md) `gcroot`

この例のコードの残りの部分は、前の`#pragma unmanaged`ディレクティブで示されているように、ネイティブ C++`main`コードです。 この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出してテーブルを作成し、テーブルの行をいくつか設定します。 ネイティブ`SAFEARRAY`型は、データベース列の ArrayIntsCol の値として渡されることに注意してください。 DatabaseClass 内では`SAFEARRAY`、これらの型は、名前空間にあるマーシャリング機能を使用してマネージ オブジェクト<xref:System.Runtime.InteropServices?displayProperty=fullName>にマーシャリングされます。 具体的には、この<xref:System.Runtime.InteropServices.Marshal.Copy%2A>メソッドを使用`SAFEARRAY`して、整数のマネージ配列にマーシャリングし、メソッド<xref:System.Runtime.InteropServices.Marshal.Copy%2A>を使用して整数のマネージ配列を`SAFEARRAY`a にマーシャリングします。

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

- コマンド ラインからコードをコンパイルするには、adonet_marshal_safearray.cpp という名前のファイルにコード例を保存し、次のステートメントを入力します。

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework のセキュリティ

ADO.NETに関連するセキュリティ問題については[、「ADO.NET アプリケーションのセキュリティ](/dotnet/framework/data/adonet/securing-ado-net-applications)保護 」を参照してください。

## <a name="related-sections"></a>関連項目

|Section|説明|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|データ アクセス サービスを .NET プログラマに公開する一連のクラスであるADO.NETの概要を示します。|

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[相互運用性](/dotnet/framework/interop/index)
