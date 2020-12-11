---
description: 詳細については、「コンパイラエラー C3199」を参照してください。
title: コンパイラエラー C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 598d21edbddc91d39edb9623dc59537d3e27bdf3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155476"
---
# <a name="compiler-error-c3199"></a>コンパイラエラー C3199

浮動小数点プラグマの使い方が無効です: 例外は、精度の低いモードではサポートされていません

[Float_control](../../preprocessor/float-control.md)プラグマは、/fp **: 精密** 以外の [/fp](../../build/reference/fp-specify-floating-point-behavior.md)設定で浮動小数点例外モデルを指定するために使用されました。

次の例では、C3199 が生成されます。

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
