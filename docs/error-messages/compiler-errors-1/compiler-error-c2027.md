---
title: コンパイラ エラー C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 901e9b791616c5684b352c1fda7687f67b895d9c
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447373"
---
# <a name="compiler-error-c2027"></a>コンパイラ エラー C2027

未定義の型 'type' の使用します。

型は、それが定義されるまで使用できません。 エラーを解決するには、型が参照する前に完全に定義されていることを必ずします。

## <a name="example"></a>例

次の例では、C2027 が生成されます。

```
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

## <a name="example"></a>例

宣言されているが未定義の型へのポインターを宣言することになります。 C++未定義の型への参照を許可しません。

次の例では、C2027 が生成されます。

```
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```