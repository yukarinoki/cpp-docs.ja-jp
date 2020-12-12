---
description: 詳細については、「コンパイラエラー C2389」を参照してください。
title: コンパイラ エラー C2389
ms.date: 11/04/2016
f1_keywords:
- C2389
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
ms.openlocfilehash: 1f9d34be47376564bf7c6fc221cf6f5b01e7850f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123969"
---
# <a name="compiler-error-c2389"></a>コンパイラ エラー C2389

'operator' : オペランド 'nullptr' は正しくありません

**`nullptr`** をオペランドにすることはできません。

次の例では C2389 が生成されます。

```cpp
// C2389.cpp
// compile with: /clr
int main() {
   throw nullptr;   // C2389
}
```
