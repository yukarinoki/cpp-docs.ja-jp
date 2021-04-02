---
description: 詳細については、「iostream」を参照してください。 &lt;&gt;
title: '&lt;iostream&gt;'
ms.date: 09/20/2017
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
helpviewer_keywords:
- iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
ms.openlocfilehash: 6bb2bd8f10e459ef91d7f358ce5e1832e9ecdb34
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099678"
---
# `<iostream>`

標準ストリームに対する読み取りと書き込みを制御するオブジェクトを宣言します。 多くの場合、このインクルードは、C++ プログラムから入力と出力を行うために必要な唯一のヘッダーです。

## <a name="syntax"></a>構文

```cpp
#include <iostream>
```

> [!NOTE]
> このライブラリでは、、、 `<iostream>` 、およびの各ステートメントを使用し `#include <ios>` `#include <streambuf>` `#include <istream>` `#include <ostream>` ます。

## <a name="remarks"></a>解説

このオブジェクトは、次の 2 つのグループに分類されます。

- [`cin`](#cin)、 [`cout`](#cout) 、 [`cerr`](#cerr) 、は [`clog`](#clog) バイト指向で、従来のバイト単位の転送を実行します。

- [`wcin`](#wcin)、 [`wcout`](#wcout) 、 [`wcerr`](#wcerr) 、 [`wclog`](#wclog) はワイド指向で、プログラムが内部で操作するワイド文字との間で変換を行います。

標準入力など、ストリームに対して特定の操作を実行すると、同じストリームで別の向きの操作を行うことはできません。 このため、プログラムはとの両方で同じように操作することはできません [`cin`](#cin) [`wcin`](#wcin) 。

このヘッダーで宣言されているすべてのオブジェクトは、特別なプロパティを共有します。を含む翻訳単位では、定義した静的オブジェクトの前に、これらのオブジェクトが構築されていると仮定でき `<iostream>` ます。 同様に、定義した静的オブジェクトのデストラクターの前に、これらのオブジェクトが破棄されないと見なすことができます。 (ただし、出力ストリームはプログラムの終了時にフラッシュされます)。そのため、プログラムの開始前とプログラムの終了後に、標準ストリームから安全に読み取りまたは書き込みを行うことができます。

ただし、この保証は一般的ではありません。 静的コンストラクターは、別の翻訳単位で、関数を呼び出す場合があります。 呼び出された関数は、このヘッダーで宣言されたオブジェクトが構築されていると想定できません。これは、静的な構築に含まれる翻訳単位の順序が不明であることを前提としています。 このようなコンテキストでこれらのオブジェクトを使用するには、最初にクラスのオブジェクトを構築する必要があり [`ios_base::Init`](../standard-library/ios-base-class.md#init) ます。

### <a name="global-stream-objects"></a>グローバル ストリーム オブジェクト

|名前|説明|
|-|-|
|[`cerr`](#cerr)|`cerr` グローバル ストリームを指定します。|
|[`cin`](#cin)|`cin` グローバル ストリームを指定します。|
|[`clog`](#clog)|`clog` グローバル ストリームを指定します。|
|[`cout`](#cout)|`cout` グローバル ストリームを指定します。|
|[`wcerr`](#wcerr)|`wcerr` グローバル ストリームを指定します。|
|[`wcin`](#wcin)|`wcin` グローバル ストリームを指定します。|
|[`wclog`](#wclog)|`wclog` グローバル ストリームを指定します。|
|[`wcout`](#wcout)|`wcout` グローバル ストリームを指定します。|

### <a name="cerr"></a><a name="cerr"></a> `cerr`

オブジェクトは、で宣言された `cerr` オブジェクトに関連付けられたストリームバッファーへの出力を制御し `stderr` `<cstdio>` ます。

```cpp
extern ostream cerr;
```

#### <a name="return-value"></a>戻り値

[`ostream`](../standard-library/ostream-typedefs.md#ostream)オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、バイト ストリームとして、標準エラー出力へのバッファリングされていない挿入を制御します。 オブジェクトが構築されると、式は `cerr.flags & unitbuf` 0 以外のとに `cerr.tie() == &cout` なります。 詳細については、「」および「」を参照してください [`cerr.flags`](../standard-library/ios-base-class.md#flags) [`unitbuf`](../standard-library/ios-functions.md#unitbuf) 。

#### <a name="example"></a>例

```cpp
// iostream_cerr.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void TestWide( )
{
   int i = 0;
   wcout << L"Enter a number: ";
   wcin >> i;
   wcerr << L"test for wcerr" << endl;
   wclog << L"test for wclog" << endl;
}

int main( )
{
   int i = 0;
   cout << "Enter a number: ";
   cin >> i;
   cerr << "test for cerr" << endl;
   clog << "test for clog" << endl;
   TestWide( );
}
```

### <a name="cin"></a><a name="cin"></a> `cin`

`cin` グローバル ストリームを指定します。

```cpp
extern istream cin;
```

#### <a name="return-value"></a>戻り値

[`istream`](../standard-library/istream-typedefs.md#istream)オブジェクト。

#### <a name="remarks"></a>解説

オブジェクトは、バイト ストリームとして標準入力からの抽出を制御します。 オブジェクトが構築されると、呼び出しは [`cin.tie`](../standard-library/basic-ios-class.md#tie) を返し [`&cout`](#cout) ます。

#### <a name="example"></a>例

この例では、は、 `cin` 数値以外の文字が含まれている場合に、ストリームの fail ビットを設定します。 プログラムは、fail ビットをクリアし、ストリームから無効な文字を除去して続行します。

```cpp
// iostream_cin.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
   int x;
   cout << "enter choice:";
   cin >> x;
   while (x < 1 || x > 4)
   {
      cout << "Invalid choice, try again:";
      cin >> x;
      // not a numeric character, probably
      // clear the failure and pull off the non-numeric character
      if (cin.fail())
      {
         cin.clear();
         char c;
         cin >> c;
      }
   }
}
```

```Output
2
```

### <a name="clog"></a><a name="clog"></a> `clog`

`clog` グローバル ストリームを指定します。

```cpp
extern ostream clog;
```

#### <a name="return-value"></a>戻り値

[`ostream`](../standard-library/ostream-typedefs.md#ostream)オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、バイト ストリームとして、標準エラー出力へのバッファリングされている挿入を制御します。

#### <a name="example"></a>例

`clog` の使用例については、[`cerr`](#cerr) を参照してください。

### <a name="cout"></a><a name="cout"></a> `cout`

`cout` グローバル ストリームを指定します。

```cpp
extern ostream cout;
```

#### <a name="return-value"></a>戻り値

[`ostream`](../standard-library/ostream-typedefs.md#ostream)オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、バイト ストリームとして、標準出力への挿入を制御します。

#### <a name="example"></a>例

`cout` の使用例については、[`cerr`](#cerr) を参照してください。

### <a name="wcerr"></a><a name="wcerr"></a> `wcerr`

`wcerr` グローバル ストリームを指定します。

```cpp
extern wostream wcerr;
```

#### <a name="return-value"></a>戻り値

[`wostream`](../standard-library/ostream-typedefs.md#wostream)オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、ワイド ストリームとして、標準エラー出力へのバッファリングされていない挿入を制御します。 オブジェクトが構築されると、式は `wcerr.flags & unitbuf` 0 以外になります。 詳細については、「」および「」を参照してください [`wcerr.flags`](../standard-library/ios-base-class.md#flags) [`unitbuf`](../standard-library/ios-functions.md#unitbuf) 。

#### <a name="example"></a>例

`wcerr` の使用例については、[`cerr`](#cerr) を参照してください。

### <a name="wcin"></a><a name="wcin"></a> `wcin`

`wcin` グローバル ストリームを指定します。

```cpp
extern wistream wcin;
```

#### <a name="return-value"></a>戻り値

[`wistream`](../standard-library/istream-typedefs.md#wistream)オブジェクト。

#### <a name="remarks"></a>解説

オブジェクトは、ワイド ストリームとして標準入力からの抽出を制御します。 オブジェクトが構築されると、呼び出しは [`wcin.tie`](../standard-library/basic-ios-class.md#tie) を返し [`&wcout`](#wcout) ます。

#### <a name="example"></a>例

`wcin` の使用例については、[`cerr`](#cerr) を参照してください。

### <a name="wclog"></a><a name="wclog"></a> `wclog`

`wclog` グローバル ストリームを指定します。

```cpp
extern wostream wclog;
```

#### <a name="return-value"></a>戻り値

[`wostream`](../standard-library/ostream-typedefs.md#wostream)オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、ワイド ストリームとして、標準エラー出力へのバッファリングされている挿入を制御します。

#### <a name="example"></a>例

`wclog` の使用例については、[`cerr`](#cerr) を参照してください。

### <a name="wcout"></a><a name="wcout"></a> `wcout`

`wcout` グローバル ストリームを指定します。

```cpp
extern wostream wcout;
```

#### <a name="return-value"></a>戻り値

[`wostream`](../standard-library/ostream-typedefs.md#wostream)オブジェクト。

#### <a name="remarks"></a>解説

このオブジェクトは、ワイド ストリームとして、標準出力への挿入を制御します。

#### <a name="example"></a>例

`wcout` の使用例については、[`cerr`](#cerr) を参照してください。

`wcout` ステートメントの `CString` インスタンスは、次の例に示されているように `const wchar_t*` にキャストする必要があります。

```cpp
CString cs("meow");

wcout <<(const wchar_t*) cs <<endl;
```

詳細については、「[CString の基本操作](../atl-mfc-shared/basic-cstring-operations.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
