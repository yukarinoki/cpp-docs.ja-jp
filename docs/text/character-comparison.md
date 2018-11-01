---
title: 文字の比較
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 206910d4b76f93a92ee5230a227d6f0346a85e61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615411"
---
# <a name="character-comparison"></a>文字の比較

次のヒントを使用します。

- ASCII 文字と既知の先頭バイトを比較することは正しく動作します。

    ```cpp
    if( *sz1 == 'A' )
    ```

- 2 つの不明な文字を比較するには、Mbstring.h で定義されているマクロのいずれかを使用する必要があります。

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   これにより、2 バイト文字の両方のバイトが等しいかどうかと比較されます。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングについて](../text/mbcs-programming-tips.md)<br/>
[バッファー オーバーフロー](../text/buffer-overflow.md)