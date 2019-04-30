---
title: コンパイラ エラー C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: d8b2366bc2899b7a2ac76b0fae133351cd88a541
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386955"
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