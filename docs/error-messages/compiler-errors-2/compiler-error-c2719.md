---
title: コンパイラ エラー C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: d635601fbf8b36218fb47c09444f3f5d023c823e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653116"
---
# <a name="compiler-error-c2719"></a>コンパイラ エラー C2719

'parameter': __declspec(align('#')) の仮引数はアラインされません。

[Align](../../cpp/align-cpp.md) `__declspec`修飾子は関数のパラメーターでは許可されていません。 関数パラメーターのアラインメントは、呼び出し規則によって制御されます。 詳細については、次を参照してください。[呼び出し規則](../../cpp/calling-conventions.md)します。

次の例は C2719 を生成し、その修正方法を示しています。

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```