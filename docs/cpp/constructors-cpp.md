---
title: コンス トラクター (C++) |Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53a05467a876a8b305aba64e49e0763cf5690a56
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940886"
---
# <a name="constructors-c"></a>コンストラクター (C++)

クラス メンバーの初期化方法をカスタマイズする場合、またはクラスのオブジェクトが作成されたときに関数を呼び出す場合は、定義、*コンス トラクター*します。 コンストラクターにはクラスと同じ名前があり、戻り値はありません。 多くのオーバー ロードされたコンス トラクターをさまざまな方法で初期化をカスタマイズする、必要に応じて定義できます。 通常、コンス トラクターにパブリック アクセシビリティを持つクラス定義または継承階層の外部のコードは、クラスのオブジェクトを作成できるようにします。 としてコンス トラクターを宣言することもできますが、**保護**または**プライベート**します。

コンス トラクターは、メンバー初期化リストを受け取る必要に応じてことができます。 これは、コンス トラクターの本体で値を割り当てるよりも、クラス メンバーを初期化するより効率的な方法です。 次の例では、クラス`Box`3 つのコンス トラクターはオーバー ロードします。 最後の 2 つは、メンバー初期化リストを使用します。

```cpp

class Box {
public:
    // Default constructor
    Box() {}

    // Initalize a Box with equal dimensions (i.e. a cube)
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

クラスのインスタンスを宣言するときに、オーバー ロードの解決の規則に基づいてどのコンス トラクターを呼び出す、コンパイラが選択されます。

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

- としてコンス トラクターを宣言することがあります**インライン**、[明示的な](#explicit_constructors)、**フレンド**または[constexpr](#constexpr_constructors)します。
- コンス トラクターとして宣言されているオブジェクトを初期化できます**const**、**揮発性**または**const volatile**します。 オブジェクトになります**const**コンス トラクターが完了後します。
- 実装ファイル内のコンス トラクターを定義する名前を付けて修飾他のメンバー関数と同様に:`Box::Box(){...}`します。

## <a name="member_init_list"></a> メンバー初期化子リスト

コンス トラクターを必要に応じて、メンバー初期化子リスト コンス トラクター本体の実行前にクラス メンバーを初期化することができます。 (メンバー初期化子の一覧と同じものではありません、*初期化子リスト*型の[std::initializer_list\<T >](../standard-library/initializer-list-class.md))。

メンバー初期化子リストを使用するは、直接のメンバーを初期化するので、コンス トラクターの本体の値より優先されます。 次の例を示しています、メンバー初期化子リストはすべての**identifier(argument)** コロンの後の式。

```cpp
  
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

識別子は、クラス メンバーを指す必要があります。引数の値で初期化されます。 引数ができるコンス トラクターのパラメーター、関数呼び出しのいずれかまたは[std::initializer_list\<T >](../standard-library/initializer-list-class.md)します。 

**const**参照型のメンバーおよびメンバーは、メンバー初期化子リストで初期化する必要があります。

パラメーター化された基本クラスのコンス トラクターの呼び出しは、基底クラスが派生コンス トラクターの実行前に完全に初期化されることを確認する初期化子リストで行ってください。

## <a name="default_constructors"></a> 既定のコンス トラクター

 *既定のコンス トラクター*通常ないパラメーターが既定値を持つパラメーターがあることができます。

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

既定のコンス トラクターはの 1 つ、[特殊なメンバー関数](special-member-functions.md)します。 クラスでコンス トラクターが宣言されていない場合、コンパイラが暗黙的なは提供**インライン**既定のコンス トラクター。

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

暗黙の既定のコンス トラクターに依存する場合は、前の例で示すように、クラス定義内のメンバーを初期化することを確認します。 これらの初期化子のないメンバーが初期化されたできなくなるし、Volume() 呼び出しガベージ値が生成されます。 一般は、暗黙の既定のコンス トラクターに依存しない場合でも、この方法でメンバーを初期化することをお勧めします。

コンパイラがその定義によって暗黙の既定のコンス トラクターを生成するように[削除](#explicitly_defaulted_and_deleted_constructors):

```cpp

    // Default constructor
    Box() = delete;

```

コンパイラによって生成された既定のコンス トラクターは、クラス メンバーが既定で構造化可能でない場合に削除済みとして定義されます。 たとえば、クラス型のすべてのメンバーとそのクラス型のメンバーは既定のコンス トラクターとデストラクターがアクセスできるになければなりません。 参照のすべてのデータ メンバー型も、 **const**メンバーは、既定のメンバー初期化子をいる必要があります。

コンパイラによって生成された既定のコンス トラクターを呼び出すかっこを使用しようとすると、警告が発行されます。

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

これは最も厄介な解析の例です。 例の式は、関数の宣言としても、既定のコンストラクターの呼び出しとしても解釈できるため、さらに、C++ パーサーが宣言を最優先に処理するため、この式は関数宣言として扱われます。 詳細については、次を参照してください。[最も厄介な解析](http://en.wikipedia.org/wiki/Most_vexing_parse)します。

既定以外のコンストラクターが宣言されている場合は、コンパイル時に既定のコンストラクターは生成されません。

```cpp
class Box {
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
};
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

ただし、一連の初期化子リストをボックス オブジェクトの配列を初期化するために使用できます。

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

詳細については、次を参照してください。[初期化子](initializers.md)します。

## <a name="copy_and_move_constructors"></a> コピー コンス トラクター

A*コピー コンス トラクター*同じ型のオブジェクトからメンバーの値をコピーして、オブジェクトを初期化します。 クラスのメンバーがスカラー値などのすべての単純型の場合は、コンパイラによって生成されたコピー コンス トラクターで十分ですする必要はありませんを定義する独自です。 クラスより複雑な初期化を必要とする場合は、カスタム コピー コンス トラクターを実装する必要があります。 たとえば、クラス メンバーがポインターの場合、必要がありますを新しいメモリを割り当てるし、その他のポイントされるオブジェクトから値をコピーするコピー コンス トラクターを定義します。 まだ新しいポインターは他のメモリ位置を指すように、コンパイラによって生成されたコピー コンス トラクターは単に、ポインターをコピーします。

コピー コンス トラクターは、これらの署名のいずれかのがあります。

```cpp

    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

コピー コンス トラクターを定義するときに、コピー代入演算子 (=) も定義する必要があります。 詳細については、次を参照してください。[割り当て](assignment.md)と[コピー コンス トラクターとコピー代入演算子](copy-constructors-and-copy-assignment-operators-cpp.md)します。

削除されたため、コピー コンス トラクターを定義することでコピーされるオブジェクトを回避できます。

```cpp
    Box (const Box& other) = delete;
```

エラーを生成するオブジェクトをコピーしようとしています。 *C2280: 削除された関数を参照しようとして*。

## <a name="move_constructors"></a> 移動コンス トラクター
A*移動コンス トラクター*は、元のデータをコピーすることがなく既存のオブジェクトのデータの所有権を新しい変数に移動する特殊なメンバー関数です。 最初のパラメーターとして右辺値参照を受け取るし、その他のパラメーターの既定値があります。 ラージ オブジェクトを渡すときに、移動コンス トラクターは、プログラムの効率を大幅に増加ことができます。 移動コンス トラクターは、最初のパラメーターとして右辺値参照を受け取ります。 その他のパラメーターは、既定値である必要があります。

```cpp
Box(Box&& other);
```

コンパイラは、リソース、別のオブジェクトが破棄する必要がなくなったを同じ型のオブジェクトを初期化中は、特定の状況で移動コンス トラクターを選択します。 次の例は、移動コンス トラクターがオーバー ロードの解決によって選択されたときに、1 つのケースを示します。 変数*ボックス*get_Box() によって返されるが、 *xvalue* (有効期限が切れる値) はスコープ外に移動しようとしています。 この例の目的を提供するには、しましょうボックスの内容を表す文字列の大規模なベクトル。 ベクトルとその文字列をコピーするではなく、移動コンス トラクター「を盗んで」、「ボックス」期限切れ間近の値からベクトルは、今すぐ新しいオブジェクトに属するようにします。 呼び出し`std::move`ために必要なすべてが両方とも`vector`と`string`クラスは、独自の移動コンス トラクターを実装します。

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

クラスは、移動コンス トラクターを定義していない場合、コンパイラは、ユーザーに宣言されたコピー コンス トラクター、コピー代入演算子、移動代入演算子またはデストラクターが存在しない場合、暗黙的なものを生成します。 明示的または暗黙的な移動コンス トラクターが定義されていない場合、移動コンス トラクターを使用して、それ以外の場合は操作はコピー コンス トラクターを代わりに使用します。 クラスは、移動コンス トラクターまたは移動代入演算子を宣言する場合、暗黙的に宣言されたコピー コンス トラクターは、削除済みとして定義されます。

暗黙的に宣言された移動コンス トラクターは、クラス型であるすべてのメンバーがないデストラクターまたは移動操作に使用するコンス トラクターをコンパイラが判断できない場合に削除済みとして定義されます。

重要な移動コンス トラクターを記述する方法の詳細については、次を参照してください。[移動コンス トラクターと移動代入演算子 (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)します。

## <a name="explicitly_defaulted_and_deleted_constructors"></a> 明示的に既定化および削除のコンス トラクター

明示的に*既定*コピー コンス トラクター、既定のコンス トラクター、移動コンス トラクター、コピー代入演算子、代入演算子、およびデストラクターを移動します。 明示的に*削除*すべての特殊なメンバー関数。

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

詳細については、次を参照してください。[明示的な既定化および削除された関数](../cpp/explicitly-defaulted-and-deleted-functions.md)します。

## <a name="constexpr_constructors"></a> constexpr コンス トラクター

コンス トラクターを宣言できる[constexpr](constexpr-cpp.md)場合

- すべての条件を満たすか、またはその既定値として宣言されているいずれかが[constexpr 関数](constexpr-cpp.md#constexpr_functions)一般的です。
- クラスに仮想基底クラスです。
- 各パラメーターは、[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types);
- 本文がない関数 try-ブロックです。
- すべての非静的データ メンバーと基本クラスのサブオブジェクトが初期化されています。
- クラスは、バリアント型のメンバーの和集合 (a) または (b) が無名共用体、共用体のメンバーの 1 つだけ初期化されます。
- constexpr コンス トラクターがあるクラス型のすべての非静的データ メンバーとすべての基底クラスのサブ オブジェクト


## <a name="init_list_constructors"></a> 初期化子リスト コンス トラクター

コンス トラクターを受け取る場合、 [std::initializer_list\<T\> ](../standard-library/initializer-list-class.md)と、そのパラメーターとその他のパラメーターは、既定の引数であると、クラスがの場合、オーバー ロードの解決でコンス トラクターを選択インスタンス化すると、直接の初期化を使用します。 Initializer_list を使用すると、それを受け入れることができるメンバーを初期化します。 たとえば、(前述したように) ボックス クラスには、`std::vector<string>`メンバー`m_contents`します。 このようなコンス トラクターを行うことができます。

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

このようなボックス オブジェクトを作成します。

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> 明示的なコンス トラクター

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

このような変換が便利な場合もありますが、微妙でありながら重大なコードのエラーにつながることが多くあります。 一般的な規則として使用する必要があります、**明示的な**キーワードでは、このような暗黙的な型変換を防ぐために、コンス トラクター (およびユーザー定義演算子)。

```cpp

explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

コンストラクターが明示的な場合、次の行ではコンパイラ エラーが発生します: `ShippingOrder so(42, 10.8);`。  詳細については、次を参照してください。[ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)します。

## <a name="order_of_construction"></a> 構築の順序

コンストラクターによる処理は次の順序で実行されます。

1. 基底クラスとメンバーのコンストラクターを宣言の順序で呼び出します。

2. クラスが仮想基底クラスから派生されている場合は、オブジェクトの仮想基底ポインターを初期化します。

3. クラスが仮想関数を含むか継承する場合は、オブジェクトの仮想関数ポインターを初期化します。 仮想関数ポインターは、クラスの仮想関数テーブルをポイントし、コードへの仮想関数呼び出しの正しいバインドを可能にします。

4. その関数本体のコードをすべて実行します。

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

```output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

派生クラスのコンストラクターは常に、基底クラスのコンストラクターを呼び出します。それにより、完全に構築された基底クラスに依存して、追加の処理を実行できるようになります。 基底クラスのコンストラクターは派生の順序で呼び出されます。たとえば、ClassA が ClassB から派生され、ClassB が ClassC から派生されている場合、まず ClassC のコンストラクター、次に ClassB のコンストラクター、最後に ClassA のコンストラクターが呼び出されます。

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

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>複数の継承を使用するクラスのコンス トラクター

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

```output

BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor

```

## <a name="virtual_functions_in_constructors"></a> コンス トラクターの仮想関数

コンストラクターの仮想関数の呼び出しは慎重に行うことをお勧めします。 基底クラスのコンストラクターは常に派生クラスのコンストラクターの前に呼び出されるため、基底コンストラクターで呼び出される関数は基底クラスのバージョンであり、派生クラスのバージョンではありません。 次の例では、`DerivedClass` を構築すると、`BaseClass` の `print_it()` 実装が行われてから、`DerivedClass` コンストラクターにより `DerivedClass` の `print_it()` 実装が行われます。

```cpp
#include <iostream>
using namespace std;

class BaseClass{
public:
    BaseClass(){
        print_it();
    }
    virtual void print_it() {
        cout << "BaseClass print_it" << endl;
    }
};

class DerivedClass : public BaseClass {
public:
    DerivedClass() {
        print_it();
    }
    virtual void print_it(){
        cout << "Derived Class print_it" << endl;
    }
};

int main() {

    DerivedClass dc;
}
```

出力を次に示します。

```output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> コンス トラクターのデリゲート

A*デリゲート コンス トラクター*初期化の処理の一部を実行する同じクラスで別のコンス トラクターを呼び出します。 これは、同様の作業を実行するすべてのある複数のコンス トラクターがある場合に便利です。 1 つのコンス トラクターでメインのロジックを記述し、他のユーザーから呼び出すことができます。 次の単純な例では、Box(int) は Box(int,int,int) に作業を委任します。

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initalize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```


コンストラクターによって作成されたオブジェクトは、コンストラクターが終了するとすぐに完全に初期化されます。 詳細については、次を参照してください。[均一な初期化とデリゲート コンス トラクター](../cpp/uniform-initialization-and-delegating-constructors.md)します。

## <a name="inheriting_constructors"></a> コンス トラクター (c++ 11) の継承

派生クラスは、次の例に示すように using 宣言を使用することにより、コンストラクターを直接基底クラスから継承できます。

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

using 宣言を使用すると、派生クラス内のコンストラクターとシグネチャが同じであるものを除き、基底クラスのすべてのコンストラクターがスコープ内に取りこまれます。 一般に、派生クラスが新しいデータ メンバーまたはコンストラクターを宣言しない場合は、コンストラクターの継承を使用することをお勧めします。

型が基底クラスを指定している場合、クラス テンプレートは型の引数からすべてのコンストラクターを継承できます。

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};

```

派生クラスは、複数の基底クラスに同じシグネチャを持つコンストラクターがある場合、複数の基底クラスからは継承できません。

## <a name="constructors_in_composite_classes"></a> コンス トラクターと複合クラス

クラス型のメンバーが含まれているクラスと呼ばれます*複合クラス*します。 複合クラスのクラス型のメンバーが作成されると、そのコンストラクターはクラス自体のコンストラクターの前に呼び出されます。 含まれるクラスに既定のコンストラクターがないときは、複合クラスのコンストラクターで初期化リストを使用する必要があります。 前に示した `StorageBox` の例で、`m_label` メンバー変数の型を新しい `Label` クラスに変更した場合、両方の基底クラスのコンストラクターを呼び出し、`m_label` のコンストラクターで `StorageBox` 変数を初期化する必要があります。

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