---
title: コンパイラ エラー C2259
ms.date: 11/04/2016
f1_keywords:
- C2259
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
ms.openlocfilehash: 0310f20854185a6f8a5ccb0ce7b087c4d7c5f29d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387072"
---
# <a name="compiler-error-c2259"></a>コンパイラ エラー C2259

'クラス' : 抽象クラスをインスタンス化できません。

抽象クラスまたは抽象構造体のインスタンスが宣言されています。

1 つ以上の純粋仮想関数を持つクラスまたは構造体をインスタンス化することはできません。 派生クラスのオブジェクトをインスタンス化するには、派生クラスが各純粋仮想関数をオーバーライドする必要があります。

詳細については、次を参照してください。[暗黙的な抽象クラス](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes)します。

次の例では、C2259 が生成されます。

```
// C2259.cpp
// compile with: /c
class V {
public:
   void virtual func() = 0;
};
class A : public V {};
class B : public V {
public:
   void func();
};
V v;  // C2259, V is an abstract class
A a;  // C2259, A inherits func() as pure virtual
B b;  // OK, B defines func()
```

インターフェイスから派生して、パブリック以外のアクセス許可を持つインターフェイス メソッドを派生クラスに実装する場合は、常に C2259 が発生する可能性があります。  これは、コンパイラでは、派生クラスに実装されたインターフェイス メソッドはパブリック アクセスを持つことが想定されているために発生します。 より制限の厳しいアクセス許可を持つインターフェイスのメンバー関数を実装する場合、コンパイラはそれらをインターフェイスに定義されるインターフェイス メソッドの実装とは見なさず、代わりにその派生クラスを抽象クラスとします。

この問題を回避する方法は 2 つあります。

- 実装されるメソッドのアクセス許可をパブリックにします。

- 派生クラスに実装されるインターフェイス メソッドに対してスコープ解決演算子を使用して、実装されるメソッド名をインターフェイスの名前で修飾します。

C2259 がビジュアルで行った準拠作業の結果として発生する可能性がもC++2005 では、 **/Zc:wchar_t**既定でになります。 このような状況で C2599 を使用してコンパイルする解決できる **/Zc:wchar_t-** を以前のバージョンから可能であれば、互換性があるため、型を更新するか、動作を取得します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。

次の例では、C2259 が生成されます。

```
// C2259b.cpp
// compile with: /c
#include <windows.h>

class MyClass {
public:
   // WCHAR now typedef'ed to wchar_t
   virtual void func(WCHAR*) = 0;
};

class MyClass2 : MyClass {
public:
   void func(unsigned short*);
};

MyClass2 x;   // C2259

// OK
class MyClass3 {
public:
   virtual void func(WCHAR*) = 0;
   virtual void func2(wchar_t*) = 0;
   virtual void func3(unsigned short*) = 0;
};

class MyClass4 : MyClass3 {
public:
   void func(WCHAR*) {}
   void func2(wchar_t*) {}
   void func3(unsigned short*) {}
};

MyClass4 y;
```

次の例では、C2259 が生成されます。

```
// C2259c.cpp
// compile with: /clr
interface class MyInterface {
   void MyMethod();
};

ref class MyDerivedClass: public MyInterface {
private:
   // Uncomment the following line to resolve.
   // public:
   void MyMethod(){}
   // or the following line
   // void MyInterface::MyMethod() {};
};

int main() {
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259
}
```
