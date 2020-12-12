---
description: '詳細情報: コンパイラの警告 (レベル 1) C4540'
title: コンパイラの警告 (レベル 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 8bd65d09abf48fc3653f160ebdf109235f3e1471
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212260"
---
# <a name="compiler-warning-level-1-c4540"></a>コンパイラの警告 (レベル 1) C4540

アクセスできない、またはあいまいなベースへの変換に使用 dynamic_castランタイムテストが失敗します (' type1 ' から ' type1 ')

**`dynamic_cast`** ある型から別の型に変換するために使用します。 コンパイラは、基底クラスにアクセスできない (インスタンス)、 **`private`** あいまいな (クラス階層に複数回出現するなど) ため、キャストが常に失敗する (NULL を返す) と判断しました。

この警告の例を次に示します。 クラス **B** はクラス **A** から派生しています。このプログラムは、を使用して **`dynamic_cast`** クラス **b** (派生クラス) からクラス **A** にキャストします。これは、クラス **b** がであり、アクセスできないため、常に失敗 **`private`** します。 へ **のアクセスを変更** すると **`public`** 、警告が解決されます。

```cpp
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
