---
title: コンパイラ エラー C2280 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
dev_langs:
- C++
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b55e07a7109c090126dfdec61bbc18bdaf5ef710
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33177646"
---
# <a name="compiler-error-c2280"></a>コンパイラ エラー c2280 を発行  
  
'*宣言*': 削除された関数を参照しようとしています。  
  
コンパイラを参照しようとしました、`deleted`関数。 このエラーとして明示的に設定されているメンバー関数への呼び出しによって発生する`= deleted`のソース コードでします。 このエラーは、構造体または自動的に宣言され、としてマークされているクラスの暗黙的な特殊なメンバー関数の呼び出しによっても発生する`deleted`コンパイラによってです。 詳細については、コンパイラが自動的に生成するときの`default`または`deleted`特殊なメンバー関数を参照してください[特殊なメンバー関数](../../cpp/special-member-functions.md)です。  
  
## <a name="example-explicitly-deleted-functions"></a>明示的に削除された関数の例。  

呼び出しを明示的に`deleted`関数は、このエラーを発生します。 明示的に`deleted`メンバー関数を意味するクラスまたは構造体は意図的にこの問題を解決するため、使用を防ぐために設計されたことを回避するコードを変更する必要があります。  
  
```cpp  
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```  
  
## <a name="example-uninitialized-data-members"></a>例: 初期化されていないデータ メンバー  
  
初期化されていない参照型のデータ メンバーまたは`const`データ メンバーには、暗黙的に宣言するコンパイラ、`deleted`既定のコンス トラクターです。 この問題を解決するには、宣言されている場合、データ メンバーを初期化します。  
  
```cpp  
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```  
  
## <a name="example-reference-and-const-data-members"></a>例: 参照、const データ メンバー  
  
A`const`宣言をコンパイラが参照型のデータ メンバーや、`deleted`コピー代入演算子。 初期化されると、これらのメンバーを代入できません、するための単純なコピーまたは移動は機能できません。 この問題を解決するには、エラーが発生する割り当て操作を削除するようなロジックを変更することをお勧めします。  
  
```cpp  
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes 
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```  
  
## <a name="example-movable-deletes-implicit-copy"></a>例: 移動が暗黙的なコピーを削除します。  
  
コンパイラが暗黙的にコピー コンス トラクターを宣言し、定義としてクラスが移動コンス トラクターまたはムーブ代入演算子を宣言していますが、コピー コンス トラクターを明示的に宣言されない場合、`deleted`です。 同様に、クラスが移動コンス トラクターまたはムーブ代入演算子を宣言していますが、コピー代入演算子を明示的に宣言されない場合、コンパイラに暗黙的に宣言コピー代入演算子と定義として`deleted`です。 この問題を解決するには、これらのメンバーを明示的に宣言する必要があります。  
 
関連してエラー C2280 が表示される、 `unique_ptr`、ほとんどの場合は、コピー コンス トラクターを呼び出すしようとしているため、`deleted`関数。 仕様では、`unique_ptr`コピーすることはできません。 所有権を転送する代わりに、移動コンス トラクターを使用します。  

```cpp  
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base  
{  
public:  
    base();  
    ~base(); 
    base(base&&); 
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this 
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};  

void copy(base *p)  
{  
    base b{*p};  // C2280
}  
```  

## <a name="example-variant-and-volatile-members"></a>例: バリアントと volatile メンバー  
  
Visual Studio 2015 Update 2 の前に、コンパイラのバージョンと生成された、非準拠の既定のコンス トラクターおよび匿名共用体のデストラクターがいました。 として暗黙的に宣言された今すぐこれら`deleted`です。 これらのバージョンにも暗黙的に定義の非準拠が許可されている`default`コピーし、移動コンス トラクターと`default`コピーし、移動代入演算子では、クラスと構造体を持つ`volatile`メンバー変数。 コンパイラは、今すぐ非自明なコンス トラクターと代入演算子を検討しを生成しない`default`実装します。 コピーと移動コンス トラクターと共用体またはクラスのコピーと移動の代入演算子が暗黙的に定義としてこのようなクラスが共用体、または、クラスの内部で匿名共用体のメンバーである、`deleted`です。 この問題を解決するには、必要な特殊なメンバー関数を明示的に宣言する必要があります。  
  
```cpp  
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {  
    A() = default;
    A(const A&);
};  

struct B {  
    union {  
        A a;  
        int i;  
    };
    // To fix this issue, declare the required 
    // special member functions:
    // B(); 
    // B(const B& b);
};  

int main() {
    B b1;  
    B b2(b1);  // C2280  
}
```  
  
## <a name="example-indirect-base-members-deleted"></a>例: 間接の基本メンバーを削除  
  
バージョンの Visual Studio 2015 Update 2 の前にコンパイラが非準拠と特殊なメンバーの関数を呼び出します間接的に派生した派生クラスを許可`private virtual`基本クラスです。 このような呼び出しが行われたときに、コンパイラはようになりましたコンパイラ エラー C2280 を発行します。  
  
この例ではクラス`top`間接的に派生した仮想プライベートから`base`です。 メンバーは、この準拠のコードで`base`にアクセスできない`top`以外の場合は、型のオブジェクト`top`既定が構築または、破棄することはできません。 古いコンパイラの動作に依存したコードでこの問題を解決するを使用する中間のクラスを変更`protected virtual`派生、または変更、`top`直接派生を使用するクラス。  

```cpp  
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base  
{  
protected:  
    base();  
    ~base();  
};  

class middle : private virtual base {}; 
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};   

void destroy(top *p)  
{  
    delete p;  // C2280  
}  
```  
  