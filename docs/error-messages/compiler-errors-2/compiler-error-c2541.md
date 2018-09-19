---
title: コンパイラ エラー C2541 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2541
dev_langs:
- C++
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 492f6f938af5e09221bff3c1c848c9688b28931d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049151"
---
# <a name="compiler-error-c2541"></a>コンパイラ エラー C2541

'delete': 削除: ポインターではないオブジェクトを削除することはできません

[削除](../../cpp/delete-operator-cpp.md)がポインターでないオブジェクトに演算子が使用されました。

次の例では、C2541 が生成されます。

```
// C2541.cpp
int main() {
   int i;
   delete i;   // C2541 i not a pointer

   // OK
   int *ip = new int;
   delete ip;
}
```