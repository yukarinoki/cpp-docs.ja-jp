---
title: ファイル システムのナビゲーション
description: C++ 標準ライブラリファイルシステム API を使用してファイルシステムをナビゲートする方法。
ms.date: 04/13/2020
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: 412d865582a14da7b8c31d9f07a43106b0c49491
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368425"
---
# <a name="file-system-navigation"></a>ファイル システムのナビゲーション

\<filesystem> ヘッダーは、File System Technical Specification ISO/IEC TS 18822:2015 (最終ドラフト: [ISO/IEC JTC 1/SC 22/WG 21 N4100](https://wg21.link/n4100)) を実装し、型および関数により、ファイル システムを移動するためのプラットフォームに依存しないコードを記述できます。 クロスプラットフォームであるため、Windows システムには関係のない API が含まれています。 たとえば、Windows`is_fifo(const path&)`では常に**false を**返します。

## <a name="overview"></a>概要

\<filesystem> API を次のタスクに使用します。

- 指定のパスの下のファイルとディレクトリを反復処理します。

- ファイルの作成時、サイズ、拡張子、およびルート ディレクトリなどに関するファイルの情報を取得します。

- パスの構成、分解、および比較

- ディレクトリの作成、コピー、および削除

- ファイルのコピーと削除

標準ライブラリを使用したファイル IO の詳細については、「[iostream プログラミング](../standard-library/iostream-programming.md)」を参照してください。

## <a name="paths"></a>パス

### <a name="constructing-and-composing-paths"></a>パスの構成および描画

(XP 以降の) Windows のパスは、ネイティブで Unicode で格納されます。 [path](../standard-library/path-class.md)クラスは、必要なすべての文字列変換を自動的に実行します。 ワイド文字配列と幅字配列の両方の引数、`std::string`および`std::wstring`UTF8 または UTF16 としてフォーマットされた型を受け取ります。 `path` クラスは、パスの区切り記号も自動的に正規化します。 コンストラクターの引数のディレクトリの区切り記号として単一のスラッシュを使用することができます。 この区切り記号を使用すると、同じ文字列を使用して、Windows 環境と UNIX 環境の両方にパスを格納できます。

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

2 つのパスを連結する際、オーバーロードされた `/` と `/=` 演算子を使用できますが、これは `+` および `+=` の `std::string` と `std::wstring`演算子と似ています。 `path`このオブジェクトは、区切り記号を指定しないと便利です。

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>パスの確認

path クラスには、パス自体のさまざまな部分に関する情報を返すメソッドがいくつかあります。 この情報は、参照するファイル・システム・エンティティーに関する情報とは異なります。 ルート、相対パス、ファイル名、および、ファイル拡張子などを取得できます。 階層内のすべてのフォルダーを確認するために、パス オブジェクトで反復処理することができます。 パス オブジェクトを反復処理する方法を次の例に示します。 また、部品に関する情報を取得する方法も説明します。

```cpp
// filesystem_path_example.cpp
// compile by using: /EHsc /W4 /permissive- /std:c++17 (or /std:c++latest)
#include <string>
#include <iostream>
#include <sstream>
#include <filesystem>

using namespace std;
using namespace std::filesystem;

wstring DisplayPathInfo()
{
    // This path may or may not refer to an existing file. We are
    // examining this path string, not file system objects.
    path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt ");

    wostringstream wos;
    int i = 0;
    wos << L"Displaying path info for: " << pathToDisplay << endl;
    for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr)
    {
        wos << L"path part: " << i++ << L" = " << *itr << endl;
    }

    wos << L"root_name() = " << pathToDisplay.root_name() << endl
        << L"root_path() = " << pathToDisplay.root_path() << endl
        << L"relative_path() = " << pathToDisplay.relative_path() << endl
        << L"parent_path() = " << pathToDisplay.parent_path() << endl
        << L"filename() = " << pathToDisplay.filename() << endl
        << L"stem() = " << pathToDisplay.stem() << endl
        << L"extension() = " << pathToDisplay.extension() << endl;

    return wos.str();
}

int main()
{
    wcout << DisplayPathInfo() << endl;
    // wcout << ComparePaths() << endl; // see following example
    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

このコードでは、次の出力が生成されます:

```Output
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt
path part: 0 = C:
path part: 1 = \
path part: 2 = FileSystemTest
path part: 3 = SubDir3
path part: 4 = SubDirLevel2
path part: 5 = File2.txt
root_name() = C:
root_path() = C:\
relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt
parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2
filename() = File2.txt
stem() = File2
extension() = .txt
```

### <a name="comparing-paths"></a>パスの比較

`path` クラスは、 `std::string` および `std::wstring`と同じ比較演算子をオーバーロードします。 2 つのパスを比較する場合、区切り記号が正規化された後に文字列比較を行います。 末尾のスラッシュ (または円記号) が欠落している場合、そのスラッシュは追加されず、比較に影響します。 パスの値を比較する方法を次の例に示します。

```cpp
wstring ComparePaths()
{
    path p0(L"C:/Documents");                 // no trailing separator
    path p1(L"C:/Documents/");                // p0 < p1
    path p2(L"C:/Documents/2013/");           // p1 < p2
    path p3(L"C:/Documents/2013/Reports/");   // p2 < p3
    path p4(L"C:/Documents/2014/");           // p3 < p4
    path p5(L"D:/Documents/2013/Reports/");   // p4 < p5

    wostringstream wos;
    wos << boolalpha <<
        p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl <<
        p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl <<
        p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl <<
        p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl <<
        p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl;
    return wos.str();
}
```

```Output
C:\Documents < C:\Documents\: true
C:\Documents\ < C:\Documents\2013\: true
C:\Documents\2013\ < C:\Documents\2013\Reports\: true
C:\Documents\2013\Reports\ < C:\Documents\2014\: true
C:\Documents\2014\ < D:\Documents\2013\Reports\: true
```

このコードを実行するには、上記の完全なサンプル コードに貼り付けて、`main` でこれを呼び出す行をコメント解除します。

### <a name="converting-between-path-and-string-types"></a>パスと文字列型の間の変換

`path` オブジェクトは `std::wstring` または `std::string`に暗黙的に変換できます。 これは、次の例に示すように[、wofstream::open](../standard-library/basic-ofstream-class.md#open)などの関数にパスを渡すことができるという意味です。

```cpp
// filesystem_path_conversion.cpp
// compile by using: /EHsc /W4 /permissive- /std:c++17 (or /std:c++latest)
#include <string>
#include <iostream>
#include <fstream>
#include <filesystem>

using namespace std;
using namespace std::filesystem;

int main()
{
    const wchar_t* p{ L"C:/Users/Public/Documents" };
    path filePath(p);

    filePath /= L"NewFile.txt";

    // Open, write to, and close the file.
    wofstream writeFile(filePath, ios::out);  // implicit conversion
    writeFile << L"Lorem ipsum\nDolor sit amet";
    writeFile.close();

    // Open, read, and close the file.
    wifstream readFile;
    wstring line;
    readFile.open(filePath);  // implicit conversions
    wcout << L"File " << filePath << L" contains:" << endl;
    while (readFile.good())
    {
        getline(readFile, line);
        wcout << line << endl;
    }
    readFile.close();

    wcout << endl << L"Press Enter to exit" << endl;
    wstring input;
    getline(wcin, input);
}
```

```Output
File C:\Users\Public\Documents\NewFile.txt contains:
Lorem ipsum
Dolor sit amet

Press Enter to exit
```

## <a name="iterating-directories-and-files"></a>ディレクトリとファイルを反復する

\<filesystem> ヘッダーは、[directory_iterator](../standard-library/directory-iterator-class.md) 型を提供して、1 つのディレクトリを反復し、[recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) クラスはディレクトリとサブディレクトリを再帰的に反復します。 `path` オブジェクトを渡して反復子を構成した後、反復子はパス内の最初の directory_entry を指します。 既定のコンストラクターを呼び出すことで、終了反復子を作成します。

ディレクトリを反復処理する場合、いくつかの種類のアイテムが見つかる場合があります。 これらの項目には、ディレクトリ、ファイル、シンボリック リンク、ソケット ファイルなどがあります。 `directory_iterator` は、[directory_entry](../standard-library/directory-entry-class.md) オブジェクトとして項目を返します。
