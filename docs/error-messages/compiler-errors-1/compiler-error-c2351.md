---
title: コンパイラ エラー C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 2d93902ee0008a54da1b2ecf165e0a829362511f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665492"
---
# <a name="compiler-error-c2351"></a>コンパイラ エラー C2351

古い C++ コンス トラクター初期化構文です。

新しいスタイルの初期化リスト コンス トラクターには、唯一の基本クラスである場合でも、各直接基底クラスを明示的に名前する必要があります。

次の例では、C2351 が生成されます。

```
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```