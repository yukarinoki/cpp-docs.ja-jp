---
title: 均一な初期化とコンストラクターのデリゲート
ms.date: 11/04/2016
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
ms.openlocfilehash: 5c5cb6421d9c8ce20f0c5e24de986ee50d9b2238
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162110"
---
# <a name="uniform-initialization-and-delegating-constructors"></a>均一な初期化とコンストラクターのデリゲート

最新の C++ で使用できます*かっこ初期化を*等号せず、任意の種類。 また、同様の作業を実行するコンストラクターが複数あるときに、デリゲート コンストラクターを使用してコードを簡単にすることもできます。

## <a name="brace-initialization"></a>かっこ初期化

任意のクラス、構造体、または共用体にかっこ初期化を使用できます。 型に既定のコンストラクターがあり、暗黙的または明示的に宣言されている場合、(空のかっこで) 既定のかっこ初期化を使用できます。 たとえば、次のクラスは、既定のかっこ初期化と既定以外のかっこ初期化を使用して初期化できます。

```cpp
#include <string>
using namespace std;

class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}
double m_double;
string m_string;
};

int main()
{
    class_a c1{};
    class_a c1_1;

    class_a c2{ "ww" };
    class_a c2_1("xx");

    // order of parameters is the same as the constructor
    class_a c3{ "yy", 4.4 };
    class_a c3_1("zz", 5.5);
}
```

クラスに既定以外のコンストラクターがある場合、クラス メンバーがかっこ初期化に表示される順序は、対応するパラメーターがコンストラクターに表示される順序になります。メンバーが宣言される順序ではありません (前の例の `class_a` と同様)。 それ以外の場合、宣言されたコンストラクターが型にないときは、メンバーがかっこ初期化に表示される順序とメンバーが宣言される順序は同じです。この場合、必要な数だけパブリック メンバーを初期化できますが、メンバーをスキップすることはできません。 次の例は、宣言されたコンストラクターがないときに、かっこ初期化で使用される順序を示しています。

```cpp
class class_d {
public:
    float m_float;
    string m_string;
    wchar_t m_char;
};

int main()
{
    class_d d1{};
    class_d d1{ 4.5 };
    class_d d2{ 4.5, "string" };
    class_d d3{ 4.5, "string", 'c' };

    class_d d4{ "string", 'c' }; // compiler error
    class_d d5("string", 'c', 2.0 }; // compiler error
}
```

既定のコンストラクターが明示的に宣言されていても、削除対象としてマークされている場合は、既定のかっこ初期化は使用できません。

```cpp
class class_f {
public:
    class_f() = delete;
    class_f(string x): m_string { x } {}
    string m_string;
};
int main()
{
    class_f cf{ "hello" };
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function
}
```

かっこ初期化を使用することができますの初期化をどこでも通常実行 — たとえば、関数パラメーターまたは戻り値として、**新しい**キーワード。

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

## <a name="initializerlist-constructors"></a>initializer_list Constructors

[Initializer_list クラス](../standard-library/initializer-list-class.md)コンス トラクターと他のコンテキストで使用できる指定された型のオブジェクトの一覧を表します。 かっこ初期化を使用して、initializer_list を構築できます。

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  このクラスを使用する必要があります、 [ \<initializer_list >](../standard-library/initializer-list.md)ヘッダー。

`initializer_list` をコピーできます。 この場合、新しいリストのメンバーは、元のリストのメンバーを参照します。

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

標準ライブラリのコンテナー クラスと、`string`、`wstring`、および `regex` にも `initializer_list` コンストラクターが含まれます。 次の例は、これらのコンストラクターでかっこ初期化を行う方法を示しています。

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{'x', 'y', 'z'};
```

## <a name="delegating-constructors"></a>デリゲート コンストラクター

多くのクラスに、パラメーターの検証など、同じような処理を実行するコンストラクターが複数含まれます。

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

繰り返し出現するコードを減らすには、すべての検証を行う関数を追加します。ただし、`class_c` のコードについては、1 つのコンストラクターが作業の一部を他にデリゲートできる方が、理解や保守が簡単になります。 デリゲート コンストラクターを追加するには、`constructor (. . .) : constructor (. . .)` 構文を使用します。

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

前の例では、`class_c(int, int, int)` コンストラクターが最初に `class_c(int, int)` コンストラクターを呼び出し、その後、この呼び出されたコンストラクターが `class_c(int)` を呼び出していることに注意してください。 各コンストラクターが、他のコンストラクターで実行されていない作業のみを行います。

オブジェクトは、呼び出された最初のコンストラクターによって初期化されるため、そのメンバーすべてがこの時点で初期化されます。 ここで示すように、他のコンストラクターにデリゲートされたコンストラクターでは、メンバーの初期化を実行できません。

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

次の例は、静的でないデータ メンバー初期化子の使用例を示しています。 コンストラクターも特定のデータ メンバーを初期化する場合は、メンバーの初期化子がオーバーライドされることに注意してください。

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

コンストラクター デリゲート構文では、コンストラクターの再帰 (Constructor1 が、Constructor1 を呼び出す Constructor2 を呼び出すなど) が誤って作成されるのを防ぐことができず、さらに、スタック オーバーフローが発生するまでエラーがスローされません。 このサイクルを回避する必要があります。

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```