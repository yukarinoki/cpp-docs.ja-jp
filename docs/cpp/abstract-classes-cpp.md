---
description: '詳細情報: 抽象クラス (C++)'
title: 抽象クラス (C++)
ms.date: 02/18/2021
helpviewer_keywords:
- classes [C++], abstract
- base classes [C++], abstract classes [C++]
- abstract classes [C++]
- derived classes [C++], abstract classes [C++]
ms.openlocfilehash: 375dd40c41a9de2b5b66a295cfccaae04d4ccbb8
ms.sourcegitcommit: 10baf2761694a7d9f478e5609f24158ed8258a44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "107282623"
---
# <a name="abstract-classes-c"></a>抽象クラス (C++)

抽象クラスは一般的な概念を表現したもので、このクラスからより具体的なクラスを派生するために使用できます。 抽象クラス型のオブジェクトを作成することはできません。 ただし、抽象クラス型へのポインターと参照を使用できます。

抽象クラスを作成するには、少なくとも1つの純粋仮想メンバー関数を宣言します。 これは、 *純粋* 指定子 () 構文を使用して宣言された仮想関数です `= 0` 。 抽象クラスから派生したクラスは純粋仮想関数を実装する必要があります。つまり派生クラスも抽象クラスです。

[仮想関数](../cpp/virtual-functions.md)に示されている例を考えてみましょう。 `Account` クラスの目的は一般的な機能を提供することですが、`Account` 型のオブジェクトは一般的すぎて役に立ちません。 これは、抽象クラスに適した候補であることを意味 `Account` します。

```cpp
// deriv_AbstractClasses.cpp
// compile with: /LD
class Account {
public:
   Account( double d );   // Constructor.
   virtual double GetBalance();   // Obtain balance.
   virtual void PrintBalance() = 0;   // Pure virtual function.
private:
    double _balance;
};
```

この宣言と前の宣言の唯一の違いは、`PrintBalance` が純粋指定子 (`= 0`) で宣言されていることです。

## <a name="restrictions-on-abstract-classes"></a>抽象クラスに関する制約

抽象クラスは、次の場合には使用できません。

- 変数またはメンバー データ

- 引数の型

- 関数の戻り値の型

- 明示的な変換の型

抽象クラスのコンストラクターが純粋仮想関数を直接または間接的に呼び出す場合、結果は未定義になります。 ただし、抽象クラスのコンストラクターとデストラクターは、他のメンバー関数を呼び出すことができます。

## <a name="defined-pure-virtual-functions"></a>定義済み純粋仮想関数

抽象クラスの純粋仮想関数は、 *定義* することも、実装することもできます。 このような関数を呼び出すことができるのは、完全修飾構文を使用する場合のみです。

*抽象クラス名*::*function-name*()

定義された純粋仮想関数は、基本クラスに純粋仮想デストラクターが含まれるクラス階層を設計するときに役立ちます。 これは、オブジェクトの破棄時に基本クラスのデストラクターが常に呼び出されるためです。 次に例を示します。

```cpp
// deriv_RestrictionsOnUsingAbstractClasses.cpp
// Declare an abstract base class with a pure virtual destructor.
// It's the simplest possible abstract class.
class base
{
public:
    base() {}
    // To define the virtual destructor outside the class:
    virtual ~base() = 0;
    // Microsoft-specific extension to define it inline:
//  virtual ~base() = 0 {};
};

base::~base() {} // required if not using Microsoft extension

class derived : public base
{
public:
    derived() {}
    ~derived() {}
};

int main()
{
    derived aDerived; // destructor called when it goes out of scope
}
```

この例では、Microsoft コンパイラ拡張機能を使用して、インライン定義を純粋仮想に追加する方法を示し `~base()` ます。 また、を使用して、クラスの外部で定義することもでき `base::~base() {}` ます。

オブジェクトがスコープ外に `aDerived` 出ると、クラスのデストラクター `derived` が呼び出されます。 コンパイラは、デストラクターの後にクラスのデストラクターを暗黙的に呼び出すコードを生成し `base` `derived` ます。 純粋仮想関数の空の実装は、 `~base` 少なくとも関数の実装が存在することを保証します。 それがない場合、リンカーは暗黙的な呼び出しに対して未解決の外部シンボルエラーを生成します。

> [!NOTE]
> 前の例では、純粋仮想関数 `base::~base` は、`derived::~derived` から暗黙的に呼び出されます。 完全修飾メンバー関数名を使用して、純粋仮想関数を明示的に呼び出すこともできます。 このような関数には実装が必要です。または、呼び出しの結果がリンク時にエラーになります。

## <a name="see-also"></a>関連項目

[継承](../cpp/inheritance-cpp.md)
