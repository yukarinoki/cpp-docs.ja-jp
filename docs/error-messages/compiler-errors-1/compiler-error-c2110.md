---
description: 詳細については、「コンパイラエラー C2110」を参照してください。
title: コンパイラ エラー C2110
ms.date: 11/04/2016
f1_keywords:
- C2110
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
ms.openlocfilehash: 76bb05ceda7eaae6887e4bfd82ee7d1917598f12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278494"
---
# <a name="compiler-error-c2110"></a>コンパイラ エラー C2110

'+': ポインターにポインターを加えようとしました

プラス ( `+` ) 演算子を使用して 2 つのポインター値を追加しようとしました。

次の例では C2110 が生成されます。

```cpp
// C2110.cpp
int main() {
   int a = 0;
   int *pa;
   int *pb;
   a = pa + pb;   // C2110
}
```
