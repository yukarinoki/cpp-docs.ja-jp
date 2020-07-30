---
title: バッファー オーバーフロー
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 71877ed770384190cb7f856567d9e7e845e3da19
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217325"
---
# <a name="buffer-overflow"></a>バッファー オーバーフロー

文字のサイズが異なると、バッファーに文字を挿入するときに問題が発生する可能性があります。 文字列の文字をバッファーにコピーする次のコードについて考えてみ `sz` `rgch` ます。

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

質問は、最後のバイトが先頭バイトをコピーしたかどうかということです。 次の例では、バッファーがオーバーフローする可能性があるため、問題は解決されません。

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

`_mbccpy`この呼び出しは、正しい操作を試行します。1または2バイトであるかどうかにかかわらず、完全な文字をコピーします。 ただし、文字が2バイト幅の場合、コピーされた最後の文字がバッファーに合わないことは考慮されません。 正しい解決策は次のとおりです。

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

このコードは、を使用し `_mbclen` て、が指す現在の文字のサイズをテストするループテストで、バッファーオーバーフローが発生する可能性があるかどうかをテストし `sz` ます。 関数を呼び出すことによって、 `_mbsnbcpy` ループ内のコードを **`while`** 1 行のコードに置き換えることができます。 次に例を示します。

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>関連項目

[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)
