---
title: 浮動小数点コプロセッサと呼び出し規則
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 09358ee36da7e5a86c214789fa7fd0687e9b8825
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231196"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則

浮動小数点コプロセッサのアセンブリルーチンを記述する場合は、浮動小数点制御ワードを保持し、 **`float`** または **`double`** 値 (関数が ST (0) で返す必要がある値) を返さない限り、コプロセッサスタックをクリーニングする必要があります。

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)
