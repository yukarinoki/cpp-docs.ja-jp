---
description: 詳細については、「コンパイラエラー C2100」を参照してください。
title: コンパイラ エラー C2100
ms.date: 11/04/2016
f1_keywords:
- C2100
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
ms.openlocfilehash: 6e63f17ed7d7cf7e77b421e4706869313a078e62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341309"
---
# <a name="compiler-error-c2100"></a>コンパイラ エラー C2100

無効な間接参照

間接演算子 ( `*` ) は、nonpointer 値に適用されます。

次の例では、C2100 が生成されます。

```cpp
// C2100.cpp
int main() {
   int r = 0, *s = 0;
   s = &r;
   *r = 200;   // C2100
   *s = 200;   // OK
}
```
