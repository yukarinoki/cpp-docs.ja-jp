---
title: コンパイラ エラー C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 2d93902ee0008a54da1b2ecf165e0a829362511f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389035"
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