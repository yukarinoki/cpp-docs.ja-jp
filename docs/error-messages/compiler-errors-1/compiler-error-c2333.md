---
description: 詳細については、「コンパイラエラー C2333」を参照してください。
title: コンパイラエラー C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: 6db3e68dd9a709abbb8153ad8b4acdaf7d4d6f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234892"
---
# <a name="compiler-error-c2333"></a>コンパイラエラー C2333

' function ': 関数宣言にエラーがあります。関数本体のスキップ

このエラーは、クラス内で定義されたメンバー関数の別のエラーの後に発生します。

次の例では、C2333 が生成されます。

```cpp
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```
