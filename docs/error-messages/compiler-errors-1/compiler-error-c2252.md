---
title: コンパイラ エラー C2252
ms.date: 11/04/2016
f1_keywords:
- C2252
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
ms.openlocfilehash: 9f24e6dfeb6544e5a6173fd844e3fe8b9ae8698e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643886"
---
# <a name="compiler-error-c2252"></a>コンパイラ エラー C2252

現在のスコープでテンプレートを明示的にインスタンス化できません。

テンプレートの明示的なインスタンス化に問題が検出されました。  たとえば、関数のテンプレートを明示的にインスタンス化できません。

次の例では、C2252 が生成されます。

```
// C2252.cpp
class A {
public:
   template <class T>
   int getit(int i , T * it ) {
      return i;
   }
   template int A::getit<double>(int i, double * it);   // C2252
   // try the following line instead
   // template <> int A::getit<double>(int i, double * it);

};

int main() {
   // cannot explicitly instantiate in function
   template int A::getit<long>(int i, long * it);   // C2252
}
```