---
title: '`<ios>` typedefs'
description: 以前のライブラリのクラスをサポートする C++ 標準テンプレートライブラリ (STL) の typedef について説明し `<ios>` `ios` `iostream` ます。
ms.date: 11/06/2020
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.openlocfilehash: 4af9636ab3317e7b81eb73dc74aef065b1287e21
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381637"
---
# <a name="ios-typedefs"></a>`<ios>` typedefs

## `ios`

は、古いライブラリのクラスをサポートして `ios` `iostream` います。

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Remarks

この型は、クラステンプレートのシノニムであり [`basic_ios`](../standard-library/basic-ios-class.md) 、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## `streamoff`

内部操作をサポートします。

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Remarks

型は符号付き整数です。 ストリームの位置指定操作でバイトオフセットを格納できるオブジェクトを表します。 この表現は、少なくとも 32 ビットあります。 必ずしもストリーム内の任意のバイト位置を表すのに十分な大きさではありません。 通常、値は `streamoff(-1)` 間違ったオフセットを示します。

## `streampos`

バッファー ポインターまたはファイル ポインターの現在の位置を保持します。

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Remarks

この型は> のシノニムです [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t` 。

### <a name="example"></a>例

```cpp
// ios_streampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ofstream x( "iostream.txt" );
   x << "testing";
   streampos y = x.tellp( );
   cout << streamoff(y) << '\n';
}
```

```Output
7
```

## `streamsize`

ストリームのサイズを表します。

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Remarks

型は、さまざまなストリーム操作に関連する要素数のカウントを格納できるオブジェクトを記述する、符号付き整数です。 この表現は、少なくとも 16 ビットあります。 必ずしもストリーム内の任意のバイト位置を表すのに十分な大きさではありません。

### <a name="example"></a>例

次のプログラムをコンパイルして実行した後、ファイルを参照し `test.txt` て設定の効果を確認し `streamsize` ます。

```cpp
// ios_streamsize.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   char a[16] = "any such text";
   ofstream x( "test.txt" );
   streamsize y = 6;
   x.write( a, y );
}
```

## `wios`

は、古いライブラリのクラスをサポートして `wios` `iostream` います。

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Remarks

この型は、クラステンプレートのシノニムであり [`basic_ios`](../standard-library/basic-ios-class.md) 、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## `wstreampos`

バッファー ポインターまたはファイル ポインターの現在の位置を保持します。

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Remarks

この型は> のシノニムです [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t` 。

### <a name="example"></a>例

```cpp
// ios_wstreampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   wofstream xw( "wiostream.txt" );
   xw << L"testing";
   wstreampos y = xw.tellp( );
   cout << y << endl;
}
```

```Output
7
```
