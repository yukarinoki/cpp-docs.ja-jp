---
title: コンパイラエラー C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 59d0e5d5a5f0957f2d73cdb863ccee9a2dd2a026
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743257"
---
# <a name="compiler-error-c2027"></a>コンパイラエラー C2027

未定義の型 ' type ' が使用されています。

型は、定義されるまで使用できません。 エラーを解決するには、型が参照前に完全に定義されていることを確認してください。

## <a name="examples"></a>例

次の例では、C2027 が生成されます。

```cpp
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

宣言されているが未定義の型へのポインターを宣言することができます。 ただし、C++ では未定義の型への参照は許可されません。

次の例では、C2027 が生成されます。

```cpp
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
