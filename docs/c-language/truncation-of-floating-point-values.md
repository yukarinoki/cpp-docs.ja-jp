---
title: 浮動小数点値の切り捨て | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, truncation
ms.assetid: 051a6e22-c636-4af8-9ac4-40160f4affca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b30700b52e7cbbbc295d6050b03283b4b45a0b08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103816"
---
# <a name="truncation-of-floating-point-values"></a>浮動小数点値の切り捨て

**ANSI 3.2.1.4** 浮動小数点数をより狭い浮動小数点数に変換するときの切り捨てまたは丸めの方向

アンダーフローが発生すると、浮動小数点変数の値はゼロに丸められます。 オーバーフローは、指定した最適化に応じて、実行時エラーが発生する場合も、予測不可能な値が生成される場合もあります。

## <a name="see-also"></a>参照

[浮動小数点演算](../c-language/floating-point-math.md)