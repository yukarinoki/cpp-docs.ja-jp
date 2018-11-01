---
title: コンパイラの警告 (レベル 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 86f6cd866f7708277ebba436ba7c076086dc9c8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473672"
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