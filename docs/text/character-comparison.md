---
title: 文字の比較 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3412939bac9dace6f3abaacda75ed73d6e60f21
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428071"
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