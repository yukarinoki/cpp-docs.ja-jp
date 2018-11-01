---
title: 浮動小数点コプロセッサと呼び出し規則
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 7e9184d66bde26ab0e2b345f8f10c2e28619fd2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625110"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則

を作成しているアセンブリ ルーチンが浮動小数点コプロセッサ場合、浮動小数点を保持する必要がある制御ワードをポイントし、返す場合を除き、コプロセッサ スタックをクリーンアップする**float**または**二重**値 (これは、関数は、ST(0)) で返す必要があります。

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)