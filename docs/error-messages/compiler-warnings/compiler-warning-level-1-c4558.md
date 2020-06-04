---
title: コンパイラの警告 (レベル 1) C4558
ms.date: 11/04/2016
f1_keywords:
- C4558
helpviewer_keywords:
- C4558
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
ms.openlocfilehash: 26bf1603588f522e2bec366586984896190f2d65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162297"
---
# <a name="compiler-warning-level-1-c4558"></a>コンパイラの警告 (レベル 1) C4558

オペランド ' value ' の値が ' 上限 ' の範囲外です

アセンブリ言語命令に渡された値が、パラメーターに指定された範囲を超えています。 値は切り捨てられます。

次の例では、C4558 が生成されます。

```cpp
// C4558.cpp
// compile with: /W1
// processor: x86
void asm_test() {
   __asm pinsrw   mm1, eax, 8;   // C4558
}

int main() {
}
```
