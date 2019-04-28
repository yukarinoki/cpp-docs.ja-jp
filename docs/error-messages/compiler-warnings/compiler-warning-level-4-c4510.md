---
title: コンパイラの警告 (レベル 4) C4510
ms.date: 11/04/2016
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 80183e9f7ef17cbc37592f36eb8db1df2be94827
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221091"
---
# <a name="compiler-warning-level-4-c4510"></a>コンパイラの警告 (レベル 4) C4510

'class': 既定のコンス トラクターを生成できませんでした

指定したクラスに対して既定のコンス トラクターを生成することはできず、ユーザー定義のコンス トラクターは作成されませんでした。 この型のオブジェクトを作成することはできません。

コンパイラが既定のコンス トラクターを生成するを妨げているいくつかの状況があるなど。

- Const データ メンバー。

- 参照であるデータ メンバー。

これらのメンバーを初期化するクラスのユーザー定義の既定のコンス トラクターを作成する必要があります。

次の例では、C4510 が生成されます。

```
// C4510.cpp
// compile with: /W4
struct A {
   const int i;
   int &j;
   A& operator=( const A& ); // C4510 expected
   // uncomment the following line to resolve this C4510
   // A(int ii, int &jj) : i(ii), j(jj) {}
};   // C4510

int main() {
}
```