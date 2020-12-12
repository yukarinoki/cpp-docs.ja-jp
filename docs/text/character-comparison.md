---
description: '詳細情報: 文字の比較'
title: 文字の比較
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 0e00e087074a70145f1a73694293edc3c522d69f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297006"
---
# <a name="character-comparison"></a>文字の比較

次のヒントを参考にしてください。

- 既知の先頭バイトと ASCII 文字の比較は正常に機能します。

    ```cpp
    if( *sz1 == 'A' )
    ```

- 2つの不明な文字を比較するには、Mbstring.h で定義されているマクロのいずれかを使用する必要があります。

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   これにより、2バイト文字の両方のバイトが等しいかどうかが比較されます。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)<br/>
[バッファーオーバーフロー](../text/buffer-overflow.md)
