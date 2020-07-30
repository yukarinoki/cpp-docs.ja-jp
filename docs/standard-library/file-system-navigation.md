---
title: ファイル システムのナビゲーション
description: C++ 標準ライブラリファイルシステム Api を使用してファイルシステムを移動する方法。
ms.date: 04/13/2020
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
ms.openlocfilehash: 26abe2fad6cacf8959507f15e967278e85254024
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203287"
---
# <a name="file-system-navigation"></a>ファイル システムのナビゲーション

\<filesystem>ヘッダーは、C++ ファイルシステムの技術仕様 iso/IEC TS 18822:2015 (最終的なドラフト: [ISO/IEC jtc 1/SC 22/WG 21 N4100](https://wg21.link/n4100)) を実装し、ファイルシステム内を移動するためのプラットフォームに依存しないコードを記述するための型と関数を備えています。 クロスプラットフォームであるため、Windows システムに関連しない Api が含まれています。 たとえば、は `is_fifo(const path&)` 常に **`false`** Windows でを返します。

## <a name="overview"></a>概要

Api は、 \<filesystem> 次のタスクに使用します。

- 指定のパスの下のファイルとディレクトリを反復処理します。

- ファイルの作成時、サイズ、拡張子、およびルート ディレクトリなどに関するファイルの情報を取得します。

- パスの構成、分解、および比較

- ディレクトリの作成、コピー、および削除

- ファイルのコピーと削除

標準ライブラリを使用したファイル IO の詳細については、「[iostream プログラミング](../standard-library/iostream-programming.md)」を参照してください。

## <a name="paths"></a>パス

### <a name="constructing-and-composing-paths"></a>パスの構成および描画

(XP 以降の) Windows のパスは、ネイティブで Unicode で格納されます。 [Path](../standard-library/path-class.md)クラスでは、すべての必要な文字列変換が自動的に行われます。 ワイド文字配列とナロー文字配列の両方の引数を受け取り、 `std::string` 型と型の両方を `std::wstring` UTF8 または UTF16 として書式設定します。 `path` クラスは、パスの区切り記号も自動的に正規化します。 コンストラクターの引数のディレクトリの区切り記号として単一のスラッシュを使用することができます。 この区切り記号を使用すると、同じ文字列を使用して、Windows と UNIX の両方の環境にパスを格納できます。

```cpp
path pathToDisplay(L"/FileSystemTest/SubDir3");     // OK!
path pathToDisplay2(L"\\FileSystemTest\\SubDir3");  // Still OK as always
path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.
```

2 つのパスを連結する際、オーバーロードされた `/` と `/=` 演算子を使用できますが、これは `+` および `+=` の `std::string` と `std::wstring`演算子と似ています。 `path`オブジェクトを使用すると、不要な場合に区切り記号を指定できます。

```cpp
path myRoot("C:/FileSystemTest");  // no trailing separator, no problem!
myRoot /= path("SubDirRoot");      // C:/FileSystemTest/SubDirRoot
```

### <a name="examining-paths"></a>パスの確認

Path クラスには、パス自体のさまざまな部分に関する情報を返すメソッドがいくつかあります。 この情報は、参照されるファイルシステムエンティティに関する情報とは異なります。 ルート、相対パス、ファイル名、および、ファイル拡張子などを取得できます。 階層内のすべてのフォルダーを確認するために、パス オブジェクトで反復処理することができます。 次の例は、パスオブジェクトを反復処理する方法を示しています。 また、その部分に関する情報を取得する方法について説明します。

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

`path` クラスは、 `std::string` および `std::wstring`と同じ比較演算子をオーバーロードします。 2つのパスを比較する場合は、区切り記号が正規化された後に文字列比較を行います。 末尾のスラッシュ (または円記号) が不足している場合は追加されず、比較に影響します。 パスの値を比較する方法を次の例に示します。

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

`path` オブジェクトは `std::wstring` または `std::string`に暗黙的に変換できます。 これは、次の例に示すように、 [wofstream:: open](../standard-library/basic-ofstream-class.md#open)などの関数にパスを渡すことができることを意味します。

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

ヘッダーは、 \<filesystem> 1 つのディレクトリを反復処理するための[directory_iterator](../standard-library/directory-iterator-class.md)型を提供し、 [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)クラスはディレクトリとそのサブディレクトリを再帰的に反復処理します。 `path` オブジェクトを渡して反復子を構成した後、反復子はパス内の最初の directory_entry を指します。 既定のコンストラクターを呼び出すことで、終了反復子を作成します。

ディレクトリの反復処理では、いくつかの種類の項目が検出される場合があります。 これらの項目には、ディレクトリ、ファイル、シンボリックリンク、ソケットファイルなどが含まれます。 `directory_iterator` は、[directory_entry](../standard-library/directory-entry-class.md) オブジェクトとして項目を返します。
