---
description: 詳細については、「コンパイラエラー C2252」を参照してください。
title: コンパイラ エラー C2252
ms.date: 11/04/2016
f1_keywords:
- C2252
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
ms.openlocfilehash: 491ec4c600ab480322917d50822ede01a08dcfb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134824"
---
# <a name="compiler-error-c2252"></a>コンパイラ エラー C2252

現在のスコープでテンプレートを明示的にインスタンス化できません

テンプレートの明示的なインスタンス化で、コンパイラによって問題が検出されました。  たとえば、関数でテンプレートを明示的にインスタンス化することはできません。

次の例では、C2252 が生成されます。

```cpp
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
