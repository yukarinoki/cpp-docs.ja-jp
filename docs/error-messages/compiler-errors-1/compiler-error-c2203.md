---
description: 詳細については、「コンパイラエラー C2203」を参照してください。
title: コンパイラ エラー C2203
ms.date: 11/04/2016
f1_keywords:
- C2203
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
ms.openlocfilehash: 98da34221da5bc054de795579d33be00fb3657cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245786"
---
# <a name="compiler-error-c2203"></a>コンパイラ エラー C2203

delete 演算子で配列の境界を指定することはできません

**/Za** (ANSI) オプションを使用すると、演算子は配列 **`delete`** 全体を削除できますが、配列の一部または特定のメンバーを削除することはできません。

次の例では、C2203 が生成されます。

```cpp
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```
