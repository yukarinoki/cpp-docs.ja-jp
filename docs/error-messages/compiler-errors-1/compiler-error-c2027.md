---
title: コンパイラ エラー C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 3f3fac9d5410595fe5653e257d97d2fd7c858545
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303490"
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

宣言されているが未定義の型へのポインターを宣言することになります。  Visual C が未定義の型への参照を許可されていません。

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