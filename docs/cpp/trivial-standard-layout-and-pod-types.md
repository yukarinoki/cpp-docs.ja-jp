---
title: 単純な場合は、標準レイアウト、POD、およびリテラルの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.topic: language-reference
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: 7a80db109df1d9aa25f471312a9ff7103b90df7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32424852"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>単純な場合は、標準レイアウト、POD、およびリテラル型

用語*レイアウト*はメモリ内のクラス、構造体または共用体型のオブジェクトのメンバーの配置方法を参照します。 場合によっては、レイアウトは、言語の仕様によって明確に定義します。 クラスまたは構造体には、仮想基底クラス、仮想関数、別のアクセス コントロールを持つメンバーなどの特定の C++ 言語機能が含まれている、コンパイラは自由に、レイアウトを選択します。 どのような最適化を実行しているによってそのレイアウトが異なるし、多くの場合オブジェクト可能性がありますいないでも位置を埋めるためのメモリの連続した領域です。 たとえば、仮想関数をクラスには、そのクラスのすべてのインスタンスは 1 つの仮想関数テーブルを共有可能性があります。 このような型が非常に便利ですが、もちろん、制限事項も備えています。 レイアウトが定義されているためにできません渡すことが、C など、他の言語で書かれたプログラムでも、連続している可能性があるため、確実にコピーできません高速に低レベルの関数となど`memcopy`か、ネットワーク経由でシリアル化します。

 C++ 14 コンパイラと C++ プログラムと、指定された型の適合性に関して、特定のメモリ レイアウトに依存する操作の理由を metaprograms を有効にする単純なクラスと構造体の 3 つのカテゴリが導入されました*自明。*、*標準レイアウト*、および*POD*または Plain Old Data です。 関数テンプレートがあります。 標準ライブラリ`is_trivial<T>`、`is_standard_layout<T>`と`is_pod<T>`特定の種類が 1 つのカテゴリに属するかどうかを決定します。

## <a name="trivial-types"></a>単純型

 コンパイラで提供されるのクラスまたは C++ での構造体または単純型は、特殊なメンバー関数を明示的に既定された場合。 連続したメモリ領域を占有します。 メンバーへの異なるアクセス指定子を持つことができます。 C++ では、コンパイラはこのような状況でメンバーを注文する方法を選択するために解放します。 そのため、このようなオブジェクトを memcopy できます。 ただし C プログラムからに確実に利用することはできません。 単純型 T の char 型または符号なしの char 型の配列にコピーし、T 変数に安全にコピーできます。 アラインメント要件のためされることパディング バイト型のメンバーの間に注意してください。

 単純型は、単純な既定のコンス トラクター、自明なコピー コンス トラクター、自明なコピー代入演算子および自明なデストラクターがあります。 各ケースで*自明*コンス トラクター、演算子、デストラクター、せず、ユーザー指定を持つクラスに属していることを意味

- 仮想関数または仮想基底クラスでは、なし

- 対応する重要なコンス トラクター/演算子/デストラクターに基底クラスを持たない

- 対応する重要なコンス トラクター/演算子/デストラクターを持つクラス型のデータ メンバーがありません。

次の例では、単純型を示します。 Trivial2 の存在することで、`Trivial2(int a, int b)`コンス トラクターは、既定のコンス トラクターを提供することが必要です。 自明として限定する型、そのコンス トラクターを明示的に既定する必要があります。

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

 クラスまたは構造体は、C 言語ではない仮想関数などの特定の C++ 言語機能を含まないし、すべてのメンバーが同じアクセス制御がある、標準レイアウト型であります。 Memcopy できるし、レイアウトが適切に定義されている C プログラムで使用できます。 標準レイアウト型では、特殊なメンバーのユーザー定義関数を持つことができます。 さらに、標準レイアウト型では、これらの特性があります。

- 仮想関数または仮想基本クラスなし

- すべての非静的データ メンバーが同じアクセス制御があります。

- クラス型のすべての非静的メンバーは、標準レイアウトです。

- 任意の基本クラスが標準レイアウトです。

- 最初の非静的データ メンバーと同じ型の基本クラスを持ちません。

- これらの条件のいずれかを満たしています。

  - 非静的データ メンバーを持つ 2 つ以上の基本クラスと、最も多く派生クラスでない非静的データ メンバーまたは

  - 非静的データ メンバーを持つ基本クラスがありません。

次のコードは、標準レイアウト型の 1 つの例を示しています。

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};

```

 最後の 2 つの要件など、コードと説明よりことができます。 次の例では、たとえベースが標準レイアウト`Derived`ために、標準的なレイアウトではない it (最派生クラス) と`Base`非静的データ メンバーを持ちます。

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

 この例では`Derived`が標準レイアウトのため`Base`非静的データ メンバーを持ちません。

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

 クラスまたは構造体は、単純なと標準レイアウトの両方が、これは、POD (Plain Old Data) 型になります。 POD 型のメモリ レイアウトが連続しているためと、各メンバーには、バイト単位でコピーできるようにする前に、宣言されたメンバーとバイナリの I/O はこれらの型よりも上位のアドレス。  Int などのスカラー型も POD 型です。 クラスは、POD 型では、非静的データ メンバーとして POD 型のみを持つことができます。

## <a name="example"></a>例

次の例は、単純な標準レイアウトの違いと POD 型。

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