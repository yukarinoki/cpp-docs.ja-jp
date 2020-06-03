---
title: コンパイラの警告 (レベル 1) C4540
ms.date: 11/04/2016
f1_keywords:
- C4540
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
ms.openlocfilehash: 859ff75bbd4b3fe248d9658495e64c0c039fbb40
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186414"
---
# <a name="compiler-warning-level-1-c4540"></a>コンパイラの警告 (レベル 1) C4540

アクセスできない、またはあいまいなベースへの変換に使用 dynamic_castランタイムテストが失敗します (' type1 ' から ' type1 ')

`dynamic_cast` を使用して、ある型から別の型に変換します。 コンパイラは、基底クラスにアクセスできない (`private`、インスタンス)、あいまいである (たとえば、クラス階層に複数回出現する) ため、キャストが常に失敗する ( **NULL**を返す) と判断しました。

この警告の例を次に示します。 クラス**B**はクラス**A**から派生しています。このプログラムは、クラス**b** (派生クラス) からクラス**A**にキャストするために `dynamic_cast` を使用します。これは、クラス**b**が `private` であり、アクセスできないため、常に失敗します。 のアクセスをパブリック**に**変更**public**すると、警告が解決されます。

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
