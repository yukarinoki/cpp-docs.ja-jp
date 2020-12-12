---
description: 詳細については、「コンパイラエラー C2719」を参照してください。
title: コンパイラエラー C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 61e01107d5681c4bab39b06b00293ecdbeb9fc9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320723"
---
# <a name="compiler-error-c2719"></a>コンパイラエラー C2719

'parameter': __declspec(align('#')) の仮引数はアラインされません。

[Align](../../cpp/align-cpp.md) **`__declspec`** 修飾子は、関数パラメーターでは許可されていません。 関数パラメーターのアラインメントは、呼び出し規則によって制御されます。 詳細については、「 [呼び出し規則](../../cpp/calling-conventions.md)」を参照してください。

次の例は C2719 を生成し、その修正方法を示しています。

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
