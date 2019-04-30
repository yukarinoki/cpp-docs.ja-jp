---
title: 仮想関数
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], virtual functions
- derived classes [C++], virtual functions
- virtual functions
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
ms.openlocfilehash: 07dfd8a602dca93c89a078b2eb69e04cf9d4a7a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393845"
---
# <a name="virtual-functions"></a>仮想関数

仮想関数は、派生クラスで再定義されるメンバー関数です。 基底クラスへのポインターまたは参照を使用して派生クラス オブジェクトを参照する場合、そのオブジェクトの仮想関数を呼び出して派生クラスのバージョンの関数を実行できます。

仮想関数では、関数の呼び出しに使用する式に関係なく、オブジェクトに対して正しい関数が呼び出されます。

基底クラスにはとして宣言された関数が含まれていますと[仮想](../cpp/virtual-cpp.md)派生クラスは、同じ関数を定義します。 派生クラスからの関数は、基底クラスへのポインターまたは参照を使用して呼び出された場合でも、派生クラスのオブジェクトに対して呼び出されます。 次の例は、`PrintBalance` 関数と 2 つの派生クラスの実装を提供する基底クラスを示しています。

```cpp
// deriv_VirtualFunctions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Account {
public:
   Account( double d ) { _balance = d; }
   virtual double GetBalance() { return _balance; }
   virtual void PrintBalance() { cerr << "Error. Balance not available for base type." << endl; }
private:
    double _balance;
};

class CheckingAccount : public Account {
public:
   CheckingAccount(double d) : Account(d) {}
   void PrintBalance() { cout << "Checking account balance: " << GetBalance() << endl; }
};

class SavingsAccount : public Account {
public:
   SavingsAccount(double d) : Account(d) {}
   void PrintBalance() { cout << "Savings account balance: " << GetBalance(); }
};

int main() {
   // Create objects of type CheckingAccount and SavingsAccount.
   CheckingAccount *pChecking = new CheckingAccount( 100.00 ) ;
   SavingsAccount  *pSavings  = new SavingsAccount( 1000.00 );

   // Call PrintBalance using a pointer to Account.
   Account *pAccount = pChecking;
   pAccount->PrintBalance();

   // Call PrintBalance using a pointer to Account.
   pAccount = pSavings;
   pAccount->PrintBalance();
}
```

このコードでは、`PrintBalance` への呼び出しは、`pAccount` が指すオブジェクトを除いて同じです。 `PrintBalance` は仮想であるため、各オブジェクトに対して定義された関数のバージョンが呼び出されます。 派生クラス `PrintBalance` と `CheckingAccount` の `SavingsAccount` 関数が、基底クラス `Account` の関数を「オーバーライド」します。

`PrintBalance` 関数のオーバーライド実装を提供しないクラスが宣言されている場合、基底クラス `Account` の既定の実装が使用されます。

派生クラスの関数は、型が同じである場合にのみ、基底クラスの仮想関数をオーバーライドします。 派生クラスの関数は、基底クラスの仮想関数と戻り値の型だけが異なると無効です。引数リストも異なっている必要があります。

ポインターまたは参照を使用して関数を呼び出すときは、次の規則が適用されます。

- 仮想関数への呼び出しは、呼び出されるオブジェクトの基になる型に従って解決されます。

- 非仮想関数への呼び出しは、ポインターまたは参照の種類によって解決されます。

この例では、ポインターを通じて呼び出されたとき、仮想関数と非仮想関数がどのように動作するかを示します。

```cpp
// deriv_VirtualFunctions2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base {
public:
   virtual void NameOf();   // Virtual function.
   void InvokingClass();   // Nonvirtual function.
};

// Implement the two functions.
void Base::NameOf() {
   cout << "Base::NameOf\n";
}

void Base::InvokingClass() {
   cout << "Invoked by Base\n";
}

class Derived : public Base {
public:
   void NameOf();   // Virtual function.
   void InvokingClass();   // Nonvirtual function.
};

// Implement the two functions.
void Derived::NameOf() {
   cout << "Derived::NameOf\n";
}

void Derived::InvokingClass() {
   cout << "Invoked by Derived\n";
}

int main() {
   // Declare an object of type Derived.
   Derived aDerived;

   // Declare two pointers, one of type Derived * and the other
   //  of type Base *, and initialize them to point to aDerived.
   Derived *pDerived = &aDerived;
   Base    *pBase    = &aDerived;

   // Call the functions.
   pBase->NameOf();           // Call virtual function.
   pBase->InvokingClass();    // Call nonvirtual function.
   pDerived->NameOf();        // Call virtual function.
   pDerived->InvokingClass(); // Call nonvirtual function.
}
```

### <a name="output"></a>出力

```Output
Derived::NameOf
Invoked by Base
Derived::NameOf
Invoked by Derived
```

`NameOf` 関数が `Base` へのポインターまたは `Derived` へのポインターを介して呼び出されるかどうかに関係なく、`Derived` に対してこの関数が呼び出されます。 `Derived` が仮想関数であり、`NameOf` と `pBase` の両方が `pDerived` 型のオブジェクトを指すため、`Derived` に対する関数を呼び出します。

としてグローバルまたは静的関数を宣言することはできませんので、仮想関数はクラス型のオブジェクトに対してのみ呼び出されると、**仮想**します。

**仮想**関数、派生クラスのオーバーライドを宣言するときに、キーワードを使用できます。 必要はありませんが、は仮想関数のオーバーライドは常に仮想です。

使用して宣言されている場合を除き、基本クラスで仮想関数を定義する必要があります、*純粋指定子*します。 (純粋仮想関数の詳細については、次を参照してください[抽象クラス](../cpp/abstract-classes-cpp.md)。)。

仮想関数呼び出し機構は、スコープ解決演算子 (`::`) を使用して、明示的に関数名を修飾することで抑制できます。 `Account` クラスに関連する前の例を考えます。 基底クラスの `PrintBalance` を呼び出すには、次のようなコードを使用します。

```cpp
CheckingAccount *pChecking = new CheckingAccount( 100.00 );

pChecking->Account::PrintBalance();  //  Explicit qualification.

Account *pAccount = pChecking;  // Call Account::PrintBalance

pAccount->Account::PrintBalance();   //  Explicit qualification.
```

前の例の `PrintBalance` への呼び出しは両方とも、仮想関数呼び出し機構を抑制します。