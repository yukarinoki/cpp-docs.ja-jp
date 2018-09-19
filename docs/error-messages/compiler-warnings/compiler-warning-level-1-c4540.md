---
title: コンパイラの警告 (レベル 1) C4540 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e3f553bd1f910c7b17e079dc1f03664c78383e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042768"
---
# <a name="compiler-warning-level-1-c4540"></a>コンパイラの警告 (レベル 1) C4540

dynamic_cast がアクセスできないか、あいまいなベース; に変換するために使用テストの実行時に、('type2' への ' type1') は失敗します

使用した`dynamic_cast`を 1 つの型から変換します。 キャストが失敗は常に、コンパイラが決定されます (返す**NULL**) 基底クラスにアクセスできないため (`private`、たとえば) またはあいまいな (が複数回、クラス階層内のインスタンス)。

この警告の例を次に示します。 クラス**B**クラスから派生**A**します。プログラムを使用して`dynamic_cast`クラスにキャストする**B** (派生クラス) をクラスに**A**、ため、常に失敗するクラス**B**は`private`のためアクセスできません。 アクセスを変更する**A**に**パブリック**警告を解決します。

```
// C4540.cpp
// compile with: /W1

struct A {
   virtual void g() {}
};

struct B : private A {
   virtual void g() {}
};

int main() {
   B b;
   A * ap = dynamic_cast<A*>(&b);   // C4540
}
```