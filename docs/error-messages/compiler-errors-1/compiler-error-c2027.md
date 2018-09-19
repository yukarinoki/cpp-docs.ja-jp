---
title: コンパイラ エラー C2027 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69aae289fbab56cd77e544118909b2d7ef72ae0c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032043"
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