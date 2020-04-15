---
title: '&lt;ios&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
ms.openlocfilehash: 0f63f65fb4c10fbe2ad538852222e6468b9061d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375402"
---
# <a name="ltiosgt-typedefs"></a>&lt;ios&gt; typedefs

## <a name="ios"></a><a name="ios"></a>Ios

従来の iostream ライブラリの ios クラスをサポートします。

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_ios](../standard-library/basic-ios-class.md)のシノニムです。

## <a name="streamoff"></a><a name="streamoff"></a>ストリームオフ

内部操作をサポートします。

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>解説

型は、さまざまなストリーム位置決め操作に関連するオフセット バイト数を格納できるオブジェクトを記述する、符号付き整数です。 この表現は、少なくとも 32 ビットあります。 これは、ストリーム内の任意のバイト位置を表すのに必ずしも十分なサイズとは限りません。 この値`streamoff(-1)`は、通常、誤ったオフセットを示します。

## <a name="streampos"></a><a name="streampos"></a>ストリームポス

バッファー ポインターまたはファイル ポインターの現在の位置を保持します。

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>解説

型は[fpos](../standard-library/fpos-class.md) <  `mbstate_t`>のシノニムです。

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
   cout << y << endl;
}
```

```Output
7
```

## <a name="streamsize"></a><a name="streamsize"></a>ストリームサイズ

ストリームのサイズを表します。

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>解説

型は、さまざまなストリーム操作に関連する要素数のカウントを格納できるオブジェクトを記述する、符号付き整数です。 この表現は、少なくとも 16 ビットあります。 これは、ストリーム内の任意のバイト位置を表すのに必ずしも十分なサイズとは限りません。

### <a name="example"></a>例

次のプログラムをコンパイルおよび実行した後に、test.txt ファイルの中身を見て、`streamsize` の設定の効果を確認します。

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

## <a name="wios"></a><a name="wios"></a>ウィオス

従来の iostream ライブラリの wios クラスをサポートします。

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_ios](../standard-library/basic-ios-class.md)のシノニムです。

## <a name="wstreampos"></a><a name="wstreampos"></a>wstreampos

バッファー ポインターまたはファイル ポインターの現在の位置を保持します。

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>解説

型は[fpos](../standard-library/fpos-class.md) <  `mbstate_t`>のシノニムです。

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
