---
description: 詳細については、「コンパイラエラー C2027」を参照してください。
title: コンパイラエラー C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 131362f2caa8da80865a9601d87cfe3a5e7ab3b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175548"
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
