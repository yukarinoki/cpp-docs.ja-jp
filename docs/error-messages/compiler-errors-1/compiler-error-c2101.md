---
description: 詳細については、「コンパイラエラー C2101」を参照してください。
title: コンパイラ エラー C2101
ms.date: 11/04/2016
f1_keywords:
- C2101
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
ms.openlocfilehash: b41aa520d0aba3970689bf0bb5d65db5effb36aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278572"
---
# <a name="compiler-error-c2101"></a>コンパイラ エラー C2101

'&' に、オペランドとしての左辺値がありません

address-of 演算子 ( `&` ) には、オペランドとして左辺値が必要です。

次の例では C2101 が生成されます。

```cpp
// C2101.cpp
int main() {
   char test;
   test = &'a';   // C2101
   test = 'a';   // OK
}
```
