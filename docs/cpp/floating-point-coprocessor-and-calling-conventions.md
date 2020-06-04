---
title: 浮動小数点コプロセッサと呼び出し規則
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: c70dd3b049ca353acc8a504df52b2c61feaf1974
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188624"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則

浮動小数点コプロセッサのアセンブリルーチンを作成する**場合は、** 浮動小数点制御ワードを保持し、浮動小数点値 (関数が ST (0) で返す必要がある **) を返さ**ない限り、コプロセッサスタックをクリーニングする必要があります。

## <a name="see-also"></a>参照

[呼び出し規約](../cpp/calling-conventions.md)
