---
description: 詳細については、「ポインターのインクリメントとデクリメント」を参照してください。
title: ポインターのインクリメントとデクリメント
ms.date: 11/04/2016
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
ms.openlocfilehash: 3c333c11c5a0b68bf013dbd374eb1cc4e5f00abc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207320"
---
# <a name="incrementing-and-decrementing-pointers"></a>ポインターのインクリメントとデクリメント

次のヒントを参考にしてください。

- リーダーバイトではなく先頭バイトをポイントします。 通常は、トレイルバイトへのポインターを持つことは安全ではありません。 通常、逆ではなく、文字列を前方にスキャンする方が安全です。

- 文字全体を移動するポインターインクリメント/デクリメント関数とマクロが用意されています。

    ```cpp
    sz1++;
    ```

   次のようになります。

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc`および関数は、文字のサイズに `_mbsdec` 関係なく、単位で適切にインクリメントおよびデクリメントし `character` ます。

- デクリメントの場合、次に示すように、文字列の先頭へのポインターが必要です。

    ```cpp
    sz2--;
    ```

   次のようになります。

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   または、次のように、ヘッドポインターが文字列内の有効な文字になる場合もあります。

    ```cpp
    sz2Head < sz2
    ```

   既知の有効な先行バイトへのポインターを持っている必要があります。

- の呼び出しを高速化するために、前の文字へのポインターを維持することもでき `_mbsdec` ます。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)<br/>
[バイトインデックス](../text/byte-indices.md)
