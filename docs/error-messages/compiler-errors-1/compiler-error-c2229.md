---
title: コンパイラ エラー C2229 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b235b5fae84ba605ecec5419f9334ccfa0a4be6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035592"
---
# <a name="compiler-error-c2229"></a>コンパイラ エラー C2229

型 'identifier' が無効なサイズが 0 の配列

構造体またはビット フィールドのメンバーには、最後のメンバーでないサイズが 0 の配列が含まれています。

構造体の最後のメンバーとして、サイズ 0 の配列を持つ、構造体を割り当てるときのサイズを指定する必要があります。

サイズ 0 の配列、構造体の最後のメンバーでない場合、コンパイラは、残りのフィールドのオフセットを計算できません。

次の例では、C2229 が生成されます。

```
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```