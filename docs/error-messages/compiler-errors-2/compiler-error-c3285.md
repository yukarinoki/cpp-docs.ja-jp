---
title: コンパイラ エラー C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: 6bc211fb2394a9a2989702c13e19bd63ea8a5ad7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381333"
---
# <a name="compiler-error-c3285"></a>コンパイラ エラー C3285

for each ステートメントは、型 'type' の変数で操作できません

`for each` ステートメントは、配列またはオブジェクト コレクションのそれぞれの要素に対して、埋め込みステートメントのグループを繰り返します。

詳細については、「 [for each, in](../../dotnet/for-each-in.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3285 が生成されます。

```
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```