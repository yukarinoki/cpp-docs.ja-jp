---
title: コンパイラの警告 (レベル 4) C4510 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4510
dev_langs:
- C++
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2aaf7286c2e900629a18d7df5824ef4b7af1f5f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048969"
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