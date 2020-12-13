---
description: 詳細については、「コンパイラエラー C3285」を参照してください。
title: コンパイラ エラー C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: d5b57b878ed47118e1857558b9d633bb5ef7286c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339333"
---
# <a name="compiler-error-c3285"></a>コンパイラ エラー C3285

for each ステートメントは、型 'type' の変数で操作できません

`for each` ステートメントは、配列またはオブジェクト コレクションのそれぞれの要素に対して、埋め込みステートメントのグループを繰り返します。

詳細については、「 [for each, in](../../dotnet/for-each-in.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3285 が生成されます。

```cpp
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```
