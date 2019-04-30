---
title: コンパイラの警告 (レベル 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 8baf3c03c87dc70a80b785d7f81cbee4e1d828f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349712"
---
# <a name="compiler-warning-level-2-c4250"></a>コンパイラの警告 (レベル 2) C4250

'class1': 'class2::member' 支配経由での継承

2 つ以上のメンバーでは、同じ名前を指定します。 1 つ`class2`は、このメンバーに含まれているその他のクラスの基本クラスであるために継承されます。

C4250 を抑制するのには、使用、[警告](../../preprocessor/warning.md)プラグマ。

仮想基底クラスは、複数の派生クラス間で共有されるため、基底クラスの名前の大部分である派生クラスでの名前。 ダイヤモンド内で継承 func の 2 つの定義が、次のクラス階層を指定するには、たとえば、: 脆弱なクラス、および主要なクラスを使用する主要な:: func() vbc::func() インスタンス。 ダイヤモンド クラス オブジェクトでは、を通じて func() の非修飾の呼び出しは、常に dominate:: func() のインスタンスを呼び出します。  脆弱なクラス func() のインスタンスを導入する場合は、どちらも優先されず、定義と呼び出しはあいまいとしてフラグが。

```
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

## <a name="example"></a>例

次の例では、C4250 が生成されます。

```
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

## <a name="example"></a>例

このサンプルより複雑な状況を示しています。 次の例では、C4250 が生成されます。

```
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```