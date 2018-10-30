---
title: MBCS のプログラミングについて |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- programming [C++], MBCS
- character sets [C++], multibyte
- MBCS [C++], programming
- multibyte characters [C++]
ms.assetid: d8ad36b8-917f-474e-8adb-69462adecd17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a88fffbfc42dd6e7386ec43e55f2013f2548b6f5
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204471"
---
# <a name="mbcs-programming-tips"></a>MBCS のプログラミングについて

新しい開発では、エンド ユーザーに表示される可能性があるすべての文字列に Unicode 文字エンコーディングを使用することをお勧めします。 MBCS は、Unicode によって置き換えられたレガシ テクノロジです。 ここでは、MBCS を使用しており、Unicode への変換が実用的でない、既存のプログラムを保守する必要がある開発者のためのヒントを提供します。 ここで紹介するヒントは、MFC を使ったアプリケーションにも、使わないアプリケーションにも適用できます。 ここでは、次の内容について説明します。

- [MBCS プログラミングにおける一般的なアドバイス](../text/general-mbcs-programming-advice.md)

- [ポインターのインクリメントとデクリメント](../text/incrementing-and-decrementing-pointers.md)

- [バイト インデックス](../text/byte-indices.md)

- [文字列の最後の文字](../text/last-character-in-a-string.md)

- [文字の代入](../text/character-assignment.md)

- [文字の比較](../text/character-comparison.md)

- [バッファー オーバーフロー](../text/buffer-overflow.md)

## <a name="see-also"></a>関連項目

[マルチバイト文字セット (MBCS) のサポート](../text/support-for-multibyte-character-sets-mbcss.md)