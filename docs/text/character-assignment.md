---
title: 文字の代入
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 0f627f88ca2b1d3533d3690cd0316ee047a327ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217312"
---
# <a name="character-assignment"></a>文字の代入

次の例では、ループによって **`while`** 文字列がスキャンされ、' X ' 以外のすべての文字が別の文字列にコピーされます。

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

このコードは、のバイトをが `sz2` 指す位置にコピー `sz1` し、 `sz1` 次のバイトを受け取るようにインクリメントします。 ただし、の次の文字 `sz2` が2バイト文字の場合、の割り当てによって `sz1` 最初のバイトのみがコピーされます。 次のコードでは、ポータブル関数を使用して文字を安全にコピーし、もう1つをインクリメントして適切にコピーしてい `sz1` `sz2` ます。

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

[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)<br/>
[文字の比較](../text/character-comparison.md)
