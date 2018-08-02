---
title: 単純な標準レイアウト、ポッド、およびリテラルの種類 |Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.topic: language-reference
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: 33b24c20c93f9bf0160536f5d6149c073c6ca7a5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464014"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>単純な標準レイアウト、ポッド、およびリテラル型

用語*レイアウト*メモリ内のクラス、構造体または共用体型のオブジェクトのメンバーの配置方法を参照します。 場合によっては、レイアウトは言語の仕様によって明確に定義します。 クラスまたは構造体には、仮想基底クラス、仮想関数、メンバーごとに異なるアクセス コントロールなどの特定の C++ 言語機能が含まれているは、自由にレイアウトを選択し、コンパイラ。 によって、どのような最適化が実行されているそのレイアウトが異なる場合があり、多くの場合オブジェクトがありますも占有メモリの連続した領域。 たとえば、仮想関数をクラスには、そのクラスのすべてのインスタンスは 1 つの仮想関数テーブルを共有可能性があります。 このような型は非常に便利ですが、もちろん、制限事項も備えています。 ことはできません、C などの他の言語で記述されたプログラムに渡されるレイアウトが定義されているため、連続していない可能性があるため、確実にコピーできません高速に低レベルの関数となど`memcopy`またはネットワーク経由でシリアル化します。

 C++ 14 コンパイラだけでなく C++ プログラムと特定のメモリ レイアウトに依存する操作のため、指定された型の適合性を判断する metaprograms を有効にするには、単純なクラスと構造体の 3 つのカテゴリがで導入されました*trivial。*、*標準レイアウト*、および*ポッド*または Plain Old Data です。 標準ライブラリは、関数テンプレート`is_trivial<T>`、`is_standard_layout<T>`と`is_pod<T>`指定された型は、特定のカテゴリに属するかどうかを決定します。

## <a name="trivial-types"></a>単純型

 コンパイラで提供がクラスまたは構造体で C++ または単純型が特殊なメンバー関数を明示的に既定された場合。 連続したメモリ領域を占有します。 メンバーごとに異なるアクセス指定子を持つことができます。 C++ では、コンパイラが自由にこのような状況でメンバーを並べ替える方法を選択します。 そのため、このようなオブジェクトを memcopy できます。 ただし C プログラムから確実に使用することはできません。 単純型 T を char または符号なしの char 型の配列にコピーし、T の変数に安全にコピーします。 配置の要件により場合もある埋め込みバイト型のメンバーの間に注意してください。

 単純型は自明な既定のコンス トラクター、単純なコピー コンス トラクター、単純なコピー代入演算子および自明なデストラクターがあります。 各ケースで*trivial*コンス トラクター、演算子、デストラクターは、ユーザー指定のないしを持つクラスに属していることを意味

- 仮想関数や、仮想基底クラスがありません。

- 対応する重要なコンス トラクター/演算子/デストラクターに基底クラスを持たない

- 対応する重要なコンス トラクター/演算子/デストラクターを持つクラス型のないデータ メンバー

次の例では、単純型を示します。 Trivial2 の有無で、`Trivial2(int a, int b)`コンス トラクターは、既定のコンス トラクターを指定することが必要です。 自明として修飾するために、型のコンス トラクターを明示的に既定する必要があります。

```cpp
struct Trivial
{
      int i;
private:
   int j;  
   };

struct Trivial2
{
   int i;
   Trivial2(int a, int b) : i(a), j(b) {}
   Trivial2() = default;
   private:
   int j;   // Different access control
};
```

## <a name="standard-layout-types"></a>標準レイアウト型

 クラスまたは構造体は、C 言語ではない仮想関数などの特定の C++ 言語機能を含まない、すべてのメンバーがある、同じ access control、標準レイアウト型になります。 Memcopy でき、レイアウトの C プログラムで使用できることは十分に定義します。 標準レイアウト型では、特殊なメンバーのユーザー定義関数を持つことができます。 さらに、標準レイアウト型では、これらの特性があります。

- 仮想関数または仮想基底クラスがありません。

- すべての非静的データ メンバーがある同じアクセス制御

- クラス型のすべての非静的メンバーは、標準レイアウトです。

- すべての基底クラスが標準レイアウトです。

- 最初の非静的データ メンバーと同じ型の基底クラスがありません。

- これらの条件のいずれかを満たしています。

  - 非静的データ メンバーを最も多く派生されたクラスと 1 つの基本クラスでない非静的データ メンバーまたは

  - 基底クラスを非静的データ メンバーがありません。

次のコードでは、標準レイアウト型の 1 つの例を示します。

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};
```

 最後の 2 つの要件など、コードと説明よりことができます。 次の例では、たとえベースが標準レイアウト、`Derived`ために、標準的なレイアウトではありません it (最派生クラス) と`Base`非静的データ メンバーが存在します。

```cpp
struct Base
{
   int i;
   int j;
};

// std::is_standard_layout<<Derived> == false!
struct Derived : public Base
{
   int x;
   int y;
};

```

 この例では`Derived`標準レイアウトは、ため`Base`非静的データ メンバーを持ちません。

```cpp
struct Base
{
   void Foo() {}
};

// std::is_standard_layout<<Derived> == true
struct Derived : public Base
{
   int x;
   int y;
};
```

 標準レイアウトになります派生場合`Base`いたデータ メンバーと`Derived`メンバー関数のみを必要があります。

## <a name="pod-types"></a>POD 型

 クラスまたは構造体は、単純なと標準レイアウトの両方が、POD (Plain Old Data) 型になります。 各メンバーがバイト単位でコピーするために、その前に宣言されたメンバーとバイナリの I/O は、これらの型で実行できるよりも上位のアドレスには、POD 型のメモリ レイアウトされる連続したです。  Int などのスカラー型も POD 型。 クラスである POD 型では、非静的データ メンバーとして POD 型のみを持つことができます。

## <a name="example"></a>例

次の例は、標準レイアウトの違いと POD 型。

```cpp
#include <type_traits>
#include <iostream>

using namespace std;

struct B
{
protected:
   virtual void Foo() {}
};

// Neither trivial nor standard-layout
struct A : B
{
      int a;
   int b;
   void Foo() override {} // Virtual function
};

// Trivial but not standard-layout
struct C
   {
      int a;
private:
   int b;   // Different access control
};

// Standard-layout but not trivial
struct D
{
   int a;
   int b;
   D() {} //User-defined constructor
};

struct POD
{
   int a;
   int b;
};

int main()
{
   cout << boolalpha;
   cout << "A is trivial is " << is_trivial<A>() << endl; // false
   cout << "A is standard-layout is " << is_standard_layout<A>() << endl;  // false

   cout << "C is trivial is " << is_trivial<C>() << endl; // true
   cout << "C is standard-layout is " << is_standard_layout<C>() << endl;  // false

   cout << "D is trivial is " << is_trivial<D>() << endl;  // false
   cout << "D is standard-layout is " << is_standard_layout<D>() << endl; // true

   cout << "POD is trivial is " << is_trivial<POD>() << endl; // true
   cout << "POD is standard-layout is " << is_standard_layout<POD>() << endl; // true

   return 0;
}
```

## <a name="literal_types"></a> リテラル型

リテラル型は、コンパイル時にレイアウトを決定できます。 リテラル型を次に示します。

- void
- スカラー型
- 参照
- Void の配列、スカラー型または参照
- 自明なデストラクターを持ち、コンストラクターを移動もコピーもしない 1 つ以上の constexpr コンストラクターを持つクラス。 さらに、すべての非静的データ メンバーと基本クラスは volatile ではなくリテラル型にする必要があります。

## <a name="see-also"></a>関連項目
 [基本的な概念](../cpp/basic-concepts-cpp.md)