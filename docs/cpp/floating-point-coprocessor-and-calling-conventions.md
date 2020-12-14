---
description: 詳細については、「浮動小数点コプロセッサと呼び出し規約」を参照してください。
title: 浮動小数点コプロセッサと呼び出し規則
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 2f68671783b8a556e787aa6637b9b5c2e5799485
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242549"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則

浮動小数点コプロセッサのアセンブリルーチンを記述する場合は、浮動小数点制御ワードを保持し、 **`float`** または **`double`** 値 (関数が ST (0) で返す必要がある値) を返さない限り、コプロセッサスタックをクリーニングする必要があります。

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)
