---
title: コンストラクター (C++)
ms.date: 12/27/2019
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: 985c63c5c937f9e85b6898cdbcc61f347688b96d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865786"
---
# <a name="constructors-c"></a>コンストラクター (C++)

クラスメンバーを初期化する方法をカスタマイズしたり、クラスのオブジェクトを作成するときに関数を呼び出したりするには、*コンストラクター*を定義します。 コンストラクターにはクラスと同じ名前があり、戻り値はありません。 さまざまな方法で初期化をカスタマイズするために必要な数だけオーバーロードされたコンストラクターを定義できます。 通常、クラス定義または継承階層の外部にあるコードでクラスのオブジェクトを作成できるように、コンストラクターにはパブリック アクセシビリティが与えられます。 ただし、コンストラクターを **protected** または **private** として宣言することもできます。

コンストラクターは、必要に応じてメンバーの init リストを受け取ることができます。 これは、コンストラクターの本文で値を割り当てるよりも、クラス メンバーを初期化する方法として効率的です。 次の例のクラス `Box` には、オーバーロードされたコンストラクターが 3 つあります。 最後の 2 つでメンバー init リストが使用されます。

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    explicit Box(int i) : m_width(i), m_length(i), m_height(i) // member init list
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}

    int Volume() { return m_width * m_length * m_height; }

private:
    // Will have value of 0 when default constructor is called.
    // If we didn't zero-init here, default constructor would
    // leave them uninitialized with garbage values.
    int m_width{ 0 };
    int m_length{ 0 };
    int m_height{ 0 };
};
```

クラスのインスタンスを宣言すると、コンパイラでは、オーバーロードの解決規則に基づいて、呼び出すコンストラクターが選択されます。

```cpp
int main()
{
    Box b; // Calls Box()

    // Using uniform initialization (preferred):
    Box b2 {5}; // Calls Box(int)
    Box b3 {5, 8, 12}; // Calls Box(int, int, int)

    // Using function-style notation:
    Box b4(2, 4, 6); // Calls Box(int, int, int)
}
```

- コンストラクターは **inline**、[explicit](#explicit_constructors)、**friend** または [constexpr](#constexpr_constructors) として宣言できます。
- コンストラクターでは、**const**、**volatile**、または **const volatile** として宣言されているオブジェクトを初期化できます。 コンストラクターが完了すると、オブジェクトが **const** になります。
- 実装ファイルでコンストラクターを定義するには、他のメンバー関数と同じように修飾名を指定します。`Box::Box(){...}` です。

## <a name="member_init_list"></a> メンバー初期化子リスト

コンストラクターには、必要に応じてメンバー初期化子リストを与えることができます。これにより、コンストラクター本文の実行前にクラス メンバーが初期化されます。 (メンバー初期化子リストは型 [std::initializer_list\<T>](../standard-library/initializer-list-class.md) の*初期化子リスト*と同じものではないことにご注意ください)

メンバーを直接初期化するので、コンストラクター本文に値を割り当てるよりも、メンバー初期化子リストを使用することをお勧めします。 次の例では、メンバー初期化子リストはコロンの後のすべての **identifier(argument)** 式で構成されています。

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

識別子はクラス メンバーを参照する必要があります。引数の値を使用して初期化されます。 引数には、コンストラクター パラメーター、関数呼び出し、または [std::initializer_list\<T>](../standard-library/initializer-list-class.md) を指定できます。

**const** メンバーと参照型のメンバーは、メンバー初期化子リストで初期化する必要があります。

パラメーター化された基底クラス コンストラクターの呼び出しは、派生コンストラクターを実行する前に基底クラスが完全に初期化されるように、初期化子リストで行う必要があります。

## <a name="default_constructors"></a> 既定のコンストラクター

*既定のコンストラクター*には通常、パラメーターはありませんが、既定値を持つパラメーターが与えられることがあります。

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

既定のコンストラクターは、[特別なメンバー関数](special-member-functions.md)の 1 つです。 コンストラクターがクラス内で宣言されていない場合は、コンパイラから暗黙的 **inline** の既定コンストラクターが与えられます。

```cpp
#include <iostream>
using namespace std;

class Box {
public:
    int Volume() {return m_width * m_height * m_length;}
private:
    int m_width { 0 };
    int m_height { 0 };
    int m_length { 0 };
};

int main() {
    Box box1; // Invoke compiler-generated constructor
    cout << "box1.Volume: " << box1.Volume() << endl; // Outputs 0
}
```

暗黙的な既定のコンストラクターを使用する場合、前の例で示したように、クラス定義でメンバーを初期化してください。 これらの初期化子がない場合、メンバーは初期化されず、Volume() 呼び出しによってガベージ値が生成されます。 一般に、暗黙的な既定のコンストラクターに依存していない場合でも、この方法でメンバーを初期化することをお勧めします。

コンパイラで暗黙的な既定のコンストラクターが生成されないようにするにはそれを [deleted](#explicitly_defaulted_and_deleted_constructors) として定義します。

```cpp
    // Default constructor
    Box() = delete;
```

コンパイラによって生成された既定のコンストラクターは、クラスメンバーが既定で構築可能でない場合、削除済みとして定義されます。 たとえば、クラス型のすべてのメンバーとそのクラス型メンバーには、既定のコンストラクターとアクセス可能なデストラクターを与える必要があります。 参照型のすべてのデータ メンバーと **const** メンバーには、既定のメンバー初期化子を与える必要があります。

コンパイラによって生成される既定のコンストラクターを呼び出し、丸かっこを使用しようとすると、次の警告が出力されます。

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

これは最も厄介な解析の例です。 例の式は、関数の宣言としても、既定のコンストラクターの呼び出しとしても解釈できるため、さらに、C++ パーサーが宣言を最優先に処理するため、この式は関数宣言として扱われます。 詳細については、「[最も厄介な解析](https://en.wikipedia.org/wiki/Most_vexing_parse)」を参照してください。

既定以外のコンストラクターが宣言されている場合は、コンパイル時に既定のコンストラクターは生成されません。

```cpp
class Box {
public:
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
private:
    int m_width;
    int m_length;
    int m_height;

};

int main(){

    Box box1(1, 2, 3);
    Box box2{ 2, 3, 4 };
    Box box3; // C2512: no appropriate default constructor available
}
```

クラスに既定のコンストラクターがない場合、そのクラスのオブジェクトの配列は、角かっこ構文を使用して構築することはできません。 たとえば、前に示したコード ブロックでは、Boxes の配列は次のように宣言することはできません。

```cpp
Box boxes[3]; // C2512: no appropriate default constructor available
```

ただし、Box オブジェクトの配列を初期化する一連の初期化リストを使用することはできます。

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

詳細については、「[初期化子](initializers.md)」を参照してください。

## <a name="copy_and_move_constructors"></a> コピー コンストラクター

"*コピー コンストラクター*" では、同じ型のオブジェクトからメンバー値をコピーすることでオブジェクトが初期化されます。 クラス メンバーがスカラー値など、すべて単純型であれば、コンパイラによって生成されるコピー コンストラクターで十分であり、独自に定義する必要はありません。 クラスでより複雑な初期化が必要な場合は、カスタム コピー コンストラクターを実装する必要があります。 たとえば、クラス メンバーがポインターである場合、コピー コンストラクターを定義して新しいメモリを割り当て、コピー元のポイント先オブジェクトから値をコピーする必要があります。 コンパイラによって生成されたコピー コンストラクターにより、ポインターがコピーされます。新しいポインターは引き続き、コピー元のメモリ位置をポイントします。

コピー コンストラクターには、次のいずれかのシグネチャが与えられます。

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

コピー コンストラクターを定義するとき、コピー代入演算子 (=) も定義してください。 詳細については、「[代入](assignment.md)」と「[コピー コンストラクターとコピー代入演算子](copy-constructors-and-copy-assignment-operators-cpp.md)」を参照してください。

コピー コンストラクターを削除済みとして定義することで、オブジェクトのコピーを禁止できます。

```cpp
    Box (const Box& other) = delete;
```

オブジェクトをコピーしようとすると、"*C2280: 削除された関数を参照しようとしています*" というエラーが表示されます。

## <a name="move_constructors"></a> 移動コンストラクター

"*移動コンストラクター*" は特殊なメンバー関数であり、元のデータをコピーせず、既存オブジェクトのデータの所有権を新しい変数に移動します。 最初のパラメーターとして rvalue 参照を受け取ります。追加のパラメーターには既定値が必要です。 移動コンストラクターを使用すると、大きなオブジェクトを渡すときにプログラムの効率を大幅に向上させることができます。

```cpp
Box(Box&& other);
```

間もなく破棄され、そのリソースを必要としなくなる同じ型の別のオブジェクトでオブジェクトが初期化される状況で、コンパイラは移動コンストラクターを選択します。 次の例は、オーバーロードの解決によって移動コンストラクターが選択された場合の 1 つのケースを示しています。 `get_Box()` を呼び出すコンストラクターでは、戻り値は *xvalue* (有効期限が切れた値) になります。 変数に割り当てられていないため、範囲の外に出ます。 この例に動機を与えるために、そのコンテンツを表す大きな文字列ベクトルを Box に与えましょう。 移動コンストラクターは、ベクトルとその文字列をコピーするのではなく、ベクトルは今度は新しいオブジェクトに属するよう、有効期限切れの値 "box" からそれを "盗み" ます。 `vector` と `string` の両方のクラスで独自の移動コンストラクターが実装されるため、`std::move` を呼び出せば十分となります。

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;

class Box {
public:
    Box() { std::cout << "default" << std::endl; }
    Box(int width, int height, int length)
       : m_width(width), m_height(height), m_length(length)
    {
        std::cout << "int,int,int" << std::endl;
    }
    Box(Box& other)
       : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        std::cout << "copy" << std::endl;
    }
    Box(Box&& other) : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        m_contents = std::move(other.m_contents);
        std::cout << "move" << std::endl;
    }
    int Volume() { return m_width * m_height * m_length; }
    void Add_Item(string item) { m_contents.push_back(item); }
    void Get_Contents()
    {
        for (const auto& item : m_contents)
        {
            cout << item << " ";
        }
    }
private:
    int m_width{ 0 };
    int m_height{ 0 };
    int m_length{ 0 };
    vector<string> m_contents;
};

Box get_Box()
{
    Box b(5, 10, 18); // "int,int,int"
    b.Add_Item("Toupee");
    b.Add_Item("Megaphone");
    b.Add_Item("Suit");

    return b;
}

int main()
{
    Box b; // "default"
    Box b1(b); // "copy"
    Box b2(get_Box()); // "move"
    cout << "b2 contents: ";
    b2.Get_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}
```

クラスで移動コンストラクターが定義されない場合、ユーザーが宣言したコピー コンストラクター、コピー代入演算子、移動代入演算子、またはデストラクターが存在しなければ、コンパイラによって暗黙的なコンストラクターが生成されます。 明示的または暗黙的な移動コンストラクターが定義されていない場合、定義されていれば移動コンストラクターを使用する操作で代わりにコピー コンストラクターが使用されます。 クラスによって移動コンストラクターまたは移動代入演算子が宣言される場合、暗黙的に宣言されたコピー コンストラクターは削除済みとして定義されます。

クラス型であるメンバーにデストラクターがないか、移動操作に使用するコンストラクターをコンパイラが決定できない場合、暗黙的に宣言された移動コンストラクターは削除済みとして定義されます。

重要な移動コンストラクターを記述する方法について詳しくは、「[移動コンストラクターと移動代入演算子 (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)」を参照してください。

## <a name="explicitly_defaulted_and_deleted_constructors"></a> 明示的に既定化したコンストラクターおよび削除したコンストラクター

コピー コンストラクター、既定のコンストラクター、移動コンストラクター、コピー代入演算子、移動代入演算子、およびデストラクターの明示的な "*既定化*" が可能です。 特殊なメンバー関数はすべて明示的に "*削除*" できます。

```cpp
class Box
{
public:
    Box2() = delete;
    Box2(const Box2& other) = default;
    Box2& operator=(const Box2& other) = default;
    Box2(Box2&& other) = default;
    Box2& operator=(Box2&& other) = default;
    //...
};
```

詳細については、「[明示的に既定化された関数および削除された関数](../cpp/explicitly-defaulted-and-deleted-functions.md)」を参照してください。

## <a name="constexpr_constructors"></a> constexpr コンストラクター

次の場合、コンストラクターは [constexpr](constexpr-cpp.md) として宣言できます。

- 宣言されているか既定化されている。あるいは一般の [constexpr functions](constexpr-cpp.md#constexpr_functions) の条件をすべて満たす。
- クラスに仮想の基底クラスがない。
- 各パラメーターが[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)である。
- 本文が関数 try ブロックではない。
- 非静的データ メンバーと基底クラス サブオブジェクトがすべて初期化されている。
- (a) クラスがバリアント メンバーを持つ和集合であるか、(b) クラスに匿名の和集合が与えられている場合、和集合メンバーのいずれかのみ初期化される。
- クラス型の非静的データ メンバーと基底クラス サブオブジェクトのすべての constexpr constructor が与えられている

## <a name="init_list_constructors"></a> 初期化子リスト コンストラクター

コンストラクターがそのパラメーターとして [std::initializer_list\<T\>](../standard-library/initializer-list-class.md) を受け取るとき、他のパラメーターに既定の引数が与えられている場合、そのコンストラクターは、直接の初期化でクラスがインスタンス化されるとき、オーバーロードの解決で選択されます。 initializer_list を使用し、それを受け取ることができるすべてのメンバーを初期化できます。 たとえば、(前に示した) Box クラスに `std::vector<string>` メンバー `m_contents` があるとします。 次のようなコンストラクターを指定できます。

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

次のように Box オブジェクトを作成します。

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> 明示的なコンストラクター

クラスが 1 つのパラメーターを持つコンストラクターを含む場合、または 1 つを除くすべてのパラメーターに既定値がある場合は、パラメーター型をクラス型へ暗黙的に変換できます。 `Box` クラスに次のようなコンストラクターがある場合を例に説明します。

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

次のように、ボックスを初期化することができます。

```cpp
Box b = 42;
```

または、int をボックスを受け取る関数に渡します。

```cpp
class ShippingOrder
{
public:
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}

private:
    Box m_box;
    double m_postage;
}
//elsewhere...
    ShippingOrder so(42, 10.8);
```

このような変換が便利な場合もありますが、微妙でありながら重大なコードのエラーにつながることが多くあります。 一般的な規則としては、このような暗黙の型変換を防ぐために、コンストラクター (とユーザー定義演算子) で **explicit** キーワードを使用する必要があります。

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

コンストラクターが明示的な場合、次の行ではコンパイラ エラーが発生します: `ShippingOrder so(42, 10.8);`。  詳細については、「[ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)」を参照してください。

## <a name="order_of_construction"></a> 構築の順序

コンストラクターによる処理は次の順序で実行されます。

1. 基底クラスとメンバーのコンストラクターを宣言の順序で呼び出します。

1. クラスが仮想基底クラスから派生されている場合は、オブジェクトの仮想基底ポインターを初期化します。

1. クラスが仮想関数を含むか継承する場合は、オブジェクトの仮想関数ポインターを初期化します。 仮想関数ポインターは、クラスの仮想関数テーブルをポイントし、コードへの仮想関数呼び出しの正しいバインドを可能にします。

1. その関数本体のコードをすべて実行します。

次の例に、基底クラスとメンバーのコンストラクターが派生クラスのコンストラクターで呼び出される順序を示します。 まず、基底コンストラクターが呼び出され、基底クラスのメンバーがクラス宣言内の出現順に初期化されて、その後に派生コンストラクターが呼び出されます。

```cpp
#include <iostream>

using namespace std;

class Contained1 {
public:
    Contained1() { cout << "Contained1 ctor\n"; }
};

class Contained2 {
public:
    Contained2() { cout << "Contained2 ctor\n"; }
};

class Contained3 {
public:
    Contained3() { cout << "Contained3 ctor\n"; }
};

class BaseContainer {
public:
    BaseContainer() { cout << "BaseContainer ctor\n"; }
private:
    Contained1 c1;
    Contained2 c2;
};

class DerivedContainer : public BaseContainer {
public:
    DerivedContainer() : BaseContainer() { cout << "DerivedContainer ctor\n"; }
private:
    Contained3 c3;
};

int main() {
    DerivedContainer dc;
}
```

出力を次に示します。

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

派生クラスのコンストラクターは常に、基底クラスのコンストラクターを呼び出します。それにより、完全に構築された基底クラスに依存して、追加の処理を実行できるようになります。 基底クラスのコンストラクターは派生の順序で呼び出されます。たとえば、`ClassA` が `ClassB` から派生され、ClassB が `ClassC` から派生されている場合、まず `ClassC` のコンストラクター、次に `ClassB` のコンストラクター、最後に `ClassA` のコンストラクターが呼び出されます。

基底クラスに既定のコンストラクターがない場合は、派生クラスのコンストラクターで基底クラスのコンストラクターのパラメーターを指定する必要があります。

```cpp
class Box {
public:
    Box(int width, int length, int height){
       m_width = width;
       m_length = length;
       m_height = height;
    }

private:
    int m_width;
    int m_length;
    int m_height;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){
        m_label = label;
    }
private:
    string m_label;
};

int main(){

    const string aLabel = "aLabel";
    StorageBox sb(1, 2, 3, aLabel);
}
```

コンストラクターが例外をスローした場合、破棄の順序はコンストラクションの順序と逆になります。

1. コンストラクター関数本体のコードがアンワインドされます。

1. 基底クラスとメンバーのオブジェクトが宣言とは逆の順序で破棄されます。

1. コンストラクターがデリゲート コンストラクターでない場合は、完全に構築されたすべての基底クラスのオブジェクトとメンバーが破棄されます。 ただし、オブジェクト自体が完全に構築されていないため、デストラクターは実行されません。

## <a name="extended_aggregate"></a> 派生コンストラクターと拡張集約初期化

基底クラスのコンストラクターがパブリックではないが、派生クラスからアクセスできる場合、Visual Studio 2017 以降の **/std:c++17** モードでは、空のかっこを使用して派生型のオブジェクトを初期化することができません。

次の例では、C++14 の準拠ビヘイビアーを示します。

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};

Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

C++17 で、`Derived` は集約型と見なされるようになりました。 つまり、既定のプライベート コンストラクターによる `Base` の初期化は、集約初期化ルールの一部として直接実行されます。 以前、`Base` プライベート コンストラクターは `Derived` コンストラクターを介して呼び出され、friend 宣言があるために成功していました。

次の例では、Visual Studio 2017 以降の C++17 ビヘイビアーを **/std:c++17** モードで示しています。

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};

Derived d1; // OK. No aggregate init involved.

Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>多重継承を使用するクラスのコンストラクター

クラスが複数の基底クラスから派生されている場合、基底クラスのコンストラクターは、派生クラスの宣言で示されている順序で呼び出されます。

```cpp
#include <iostream>
using namespace std;

class BaseClass1 {
public:
    BaseClass1() { cout << "BaseClass1 ctor\n"; }
};
class BaseClass2 {
public:
    BaseClass2() { cout << "BaseClass2 ctor\n"; }
};
class BaseClass3 {
public:
    BaseClass3() { cout << "BaseClass3 ctor\n"; }
};
class DerivedClass : public BaseClass1,
                     public BaseClass2,
                     public BaseClass3
                     {
public:
    DerivedClass() { cout << "DerivedClass ctor\n"; }
};

int main() {
    DerivedClass dc;
}
```

予想される出力を次に示します。

```Output
BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor
```

## <a name="delegating_constructors"></a> デリゲート コンストラクター

"*デリゲート コンストラクター*" は同じクラスの別のコンストラクターを呼び出して、初期化の処理の一部を実行します。 これは、すべてのコンストラクターで同様の処理を実行する必要がある場合に便利です。 メイン ロジックを 1 つのコンストラクターに記述し、他のコンストラクターからそれを呼び出すことができます。 次の簡単な例では、Box(int) は、その作業を Box(int,int,int) にデリゲートします。

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```

コンストラクターによって作成されたオブジェクトは、コンストラクターが終了するとすぐに完全に初期化されます。 詳細については、「[デリゲート コンストラクター](../cpp/delegating-constructors.md)」を参照してください。

## <a name="inheriting_constructors"></a> コンストラクターの継承 (C++11)

派生クラスは、次の例に示すように **using** 宣言を使用することにより、コンストラクターを直接基底クラスから継承できます。

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    Base() { cout << "Base()" << endl; }
    Base(const Base& other) { cout << "Base(Base&)" << endl; }
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }

private:
    int num;
    char letter;
};

class Derived : Base
{
public:
    // Inherit all constructors from Base
    using Base::Base;

private:
    // Can't initialize newMember from Base constructors.
    int newMember{ 0 };
};

int main()
{
    cout << "Derived d1(5) calls: ";
    Derived d1(5);
    cout << "Derived d1('c') calls: ";
    Derived d2('c');
    cout << "Derived d3 = d2 calls: " ;
    Derived d3 = d2;
    cout << "Derived d4 calls: ";
    Derived d4;
}

/* Output:
Derived d1(5) calls: Base(int)
Derived d1('c') calls: Base(char)
Derived d3 = d2 calls: Base(Base&)
Derived d4 calls: Base()*/
```

::: moniker range=">=vs-2017"

**Visual Studio 2017 以降**: **/std:c++17** モードの **using** 宣言を使用すると、派生クラス内のコンストラクターとシグネチャが同じであるものを除き、基底クラスのすべてのコンストラクターがスコープ内に取りこまれます。 一般に、派生クラスが新しいデータ メンバーまたはコンストラクターを宣言しない場合は、コンストラクターの継承を使用することをお勧めします。 「[Visual Studio 2017 バージョン 15.7 での機能強化](https://docs.microsoft.com/cpp/overview/cpp-conformance-improvements?view=vs-2017#improvements_157)」も参照してください。

::: moniker-end

型が基底クラスを指定している場合、クラス テンプレートは型の引数からすべてのコンストラクターを継承できます。

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

派生クラスは、複数の基底クラスに同じシグネチャを持つコンストラクターがある場合、複数の基底クラスからは継承できません。

## <a name="constructors_in_composite_classes"></a> コンストラクターと複合クラス

クラス型のメンバーを含むクラスは "*複合クラス*" と呼ばれます。 複合クラスのクラス型のメンバーが作成されると、そのコンストラクターはクラス自体のコンストラクターの前に呼び出されます。 含まれるクラスに既定のコンストラクターがないときは、複合クラスのコンストラクターで初期化リストを使用する必要があります。 前に示した `StorageBox` の例で、`m_label` メンバー変数の型を新しい `Label` クラスに変更した場合、両方の基底クラスのコンストラクターを呼び出し、`m_label` のコンストラクターで `StorageBox` 変数を初期化する必要があります。

```cpp
class Label {
public:
    Label(const string& name, const string& address) { m_name = name; m_address = address; }
    string m_name;
    string m_address;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, Label label)
        : Box(width, length, height), m_label(label){}
private:
    Label m_label;
};

int main(){
// passing a named Label
    Label label1{ "some_name", "some_address" };
    StorageBox sb1(1, 2, 3, label1);

    // passing a temporary label
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });

    // passing a temporary label as an initializer list
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});
}
```

## <a name="in-this-section"></a>このセクションの内容

- [コピー コンストラクターとコピー代入演算子](copy-constructors-and-copy-assignment-operators-cpp.md)
- [移動コンストラクターと移動代入演算子](move-constructors-and-move-assignment-operators-cpp.md)
- [デリゲート コンストラクター](delegating-constructors.md)

## <a name="see-also"></a>関連項目

[クラスと構造体](classes-and-structs-cpp.md)
