---
title: 文字の代入
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 9099382a212f9f7bd6c071f4e4d9a0c2bc8887de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435374"
---
# <a name="character-assignment"></a>文字の代入

これで、次の例を検討してください、**中に**ループは、別の文字列に 'X' 以外のすべての文字をコピー、文字列をスキャンします。

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

コードのコピーにあるバイト`sz2`によって示される場所に`sz1`、インクリメントし、`sz1`次のバイトを受信します。 場合の次の文字`sz2`2 バイト文字への代入は`sz1`最初のバイトのみをコピーします。 次のコードは、文字を安全にコピーする移植可能な関数とにインクリメント`sz1`と`sz2`正しく。

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
    {
        _mbscpy_s( sz1, 1, sz2 );
        sz1 = _mbsinc( sz1 );
        sz2 = _mbsinc( sz2 );
    }
    else
        sz2 = _mbsinc( sz2 );
}
```

## <a name="see-also"></a>関連項目

[MBCS のプログラミングについて](../text/mbcs-programming-tips.md)<br/>
[文字の比較](../text/character-comparison.md)