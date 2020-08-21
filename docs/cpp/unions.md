---
title: union
description: C++ の標準の union class 型とキーワード、その使用法と制限事項について説明します。
ms.date: 08/18/2020
f1_keywords:
- union_cpp
helpviewer_keywords:
- class type [C++], union as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
no-loc:
- union
- struct
- enum
- class
- static
ms.openlocfilehash: a4dc07df5e7858dffe62478509ee1d8dc759ce96
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722181"
---
# `union`

> [!NOTE]
> C++ 17 以降では、は `std::variant` class のタイプセーフな代替です union 。

**`union`** はユーザー定義型で、すべてのメンバーが同じメモリ位置を共有します。 この定義は、任意の時点で、が union メンバーの一覧から1つ以上のオブジェクトを含むことができないことを意味します。 また、に含まれるメンバーの数に関係なく、 union 常に、最大のメンバーを格納するのに十分なメモリのみが使用されることを意味します。

は、 union 多数のオブジェクトがあり、メモリが限られている場合にメモリを節約するために役立ちます。 ただし、を union 正しく使用するには、特別な注意が必要です。 自分が割り当てたのと同じメンバーに常にアクセスできるようにする責任があります。 いずれかのメンバー型に自明でないまたはが含まれている場合は struct 、そのメンバーを明示的に使用して破棄するために、追加のコードを記述する必要があり struct ます。 を使用する前に union 、解決しようとしている問題が、基本 class 型と派生型を使用してより適切に表現できるかどうかを検討してください class 。

## <a name="syntax"></a>構文

> **`union`***`tag`* <sub>opt</sub> **`{`** 選択 *`member-list`***`};`**

### <a name="parameters"></a>パラメーター

*`tag`*<br/>
に指定された型名 union 。

*`member-list`*<br/>
に union 格納できるメンバー。

## <a name="declare-a-no-locunion"></a>を宣言する union

キーワードを使用しての宣言を開始 union **`union`** し、メンバーリストを中かっこで囲みます。

```cpp
// declaring_a_union.cpp
union RecordType    // Declare a simple union type
{
    char   ch;
    int    i;
    long   l;
    float  f;
    double d;
    int *int_ptr;
};

int main()
{
    RecordType t;
    t.i = 5; // t holds an int
    t.f = 7.25; // t now holds a float
}
```

## <a name="use-a-no-locunion"></a>使用する union

前の例では、にアクセスするすべてのコードが、データを保持して union いるメンバーを認識している必要があります。 この問題の最も一般的な解決策は、*判別 union *と呼ばれます。 でを囲み、に union struct 現在格納されている enum メンバーの型を示すメンバーを含め union ます。 次の例に、基本的なパターンを示します。

```cpp
#include <queue>

using namespace std;

enum class WeatherDataType
{
    Temperature, Wind
};

struct TempData
{
    int StationId;
    time_t time;
    double current;
    double max;
    double min;
};

struct WindData
{
    int StationId;
    time_t time;
    int speed;
    short direction;
};

struct Input
{
    WeatherDataType type;
    union
    {
        TempData temp;
        WindData wind;
    };
};

// Functions that are specific to data types
void Process_Temp(TempData t) {}
void Process_Wind(WindData w) {}

void Initialize(std::queue<Input>& inputs)
{
    Input first;
    first.type = WeatherDataType::Temperature;
    first.temp = { 101, 1418855664, 91.8, 108.5, 67.2 };
    inputs.push(first);

    Input second;
    second.type = WeatherDataType::Wind;
    second.wind = { 204, 1418859354, 14, 27 };
    inputs.push(second);
}

int main(int argc, char* argv[])
{
    // Container for all the data records
    queue<Input> inputs;
    Initialize(inputs);
    while (!inputs.empty())
    {
        Input const i = inputs.front();
        switch (i.type)
        {
        case WeatherDataType::Temperature:
            Process_Temp(i.temp);
            break;
        case WeatherDataType::Wind:
            Process_Wind(i.wind);
            break;
        default:
            break;
        }
        inputs.pop();

    }
    return 0;
}
```

前の例では、の union に `Input` struct 名前がないため、 *匿名*と呼ばれてい union ます。 そのメンバーは、のメンバーであるかのように直接アクセスでき struct ます。 匿名の使用方法の詳細については、 union 「[匿名 union ](#anonymous_unions) 」セクションを参照してください。

前の例は、共通の基本クラスから派生した型を使用して解決できる問題を示して class class います。 コンテナー内の各オブジェクトのランタイム型に基づいてコードを分岐することができます。 コードの保守と理解は簡単ですが、を使用するよりも時間がかかることがあり union ます。 また、を使用すると、関連のない union 型を格納できます。 を union 使用すると、変数自体の型を変更することなく、格納されている値の型を動的に変更でき union ます。 たとえば、 `MyUnionType` さまざまな型の異なる値を格納する要素を持つ、の異種配列を作成できます。

この例では、を誤用するのは簡単です `Input` struct 。 データを保持するメンバーにアクセスするには、識別子を正しく使用する必要があります。 union **`private`** 次の例に示すように、と特別なアクセス機能を提供することにより、誤用を防ぐことができます。

## <a name="unrestricted-no-locunion-c11"></a>無制限 union (c++ 11)

C++ 03 以前では、型が union ユーザーによって static 指定された型でない限り、型を持つ非データメンバーを含めることができ class struct struct ます。 C++11 では、これらの制限が削除されています。 このようなメンバーをに含めた場合 union 、ユーザーによって指定されていない特殊なメンバー関数はコンパイラによって自動的にマークされ **`deleted`** ます。 unionがまたは内の匿名である場合、 union ユーザーが指定し class struct ないまたはの特殊なメンバー関数は class とし struct てマークされ **`deleted`** ます。 このケースを処理する方法を次の例に示します。 のメンバーの1つ union に、この特別な処理を必要とするメンバーがあります。

```cpp
// for MyVariant
#include <crtdbg.h>
#include <new>
#include <utility>

// for sample objects and output
#include <string>
#include <vector>
#include <iostream>

using namespace std;

struct A
{
    A() = default;
    A(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    //...
};

struct B
{
    B() = default;
    B(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    vector<int> vec;
    // ...
};

enum class Kind { None, A, B, Integer };

#pragma warning (push)
#pragma warning(disable:4624)
class MyVariant
{
public:
    MyVariant()
        : kind_(Kind::None)
    {
    }

    MyVariant(Kind kind)
        : kind_(kind)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A();
            break;
        case Kind::B:
            new (&b_) B();
            break;
        case Kind::Integer:
            i_ = 0;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    ~MyVariant()
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            a_.~A();
            break;
        case Kind::B:
            b_.~B();
            break;
        case Kind::Integer:
            break;
        default:
            _ASSERT(false);
            break;
        }
        kind_ = Kind::None;
    }

    MyVariant(const MyVariant& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(other.a_);
            break;
        case Kind::B:
            new (&b_) B(other.b_);
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    MyVariant(MyVariant&& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(move(other.a_));
            break;
        case Kind::B:
            new (&b_) B(move(other.b_));
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
    }

    MyVariant& operator=(const MyVariant& other)
    {
        if (&other != this)
        {
            switch (other.kind_)
            {
            case Kind::None:
                this->~MyVariant();
                break;
            case Kind::A:
                *this = other.a_;
                break;
            case Kind::B:
                *this = other.b_;
                break;
            case Kind::Integer:
                *this = other.i_;
                break;
            default:
                _ASSERT(false);
                break;
            }
        }
        return *this;
    }

    MyVariant& operator=(MyVariant&& other)
    {
        _ASSERT(this != &other);
        switch (other.kind_)
        {
        case Kind::None:
            this->~MyVariant();
            break;
        case Kind::A:
            *this = move(other.a_);
            break;
        case Kind::B:
            *this = move(other.b_);
            break;
        case Kind::Integer:
            *this = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
        return *this;
    }

    MyVariant(const A& a)
        : kind_(Kind::A), a_(a)
    {
    }

    MyVariant(A&& a)
        : kind_(Kind::A), a_(move(a))
    {
    }

    MyVariant& operator=(const A& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(a);
        }
        else
        {
            a_ = a;
        }
        return *this;
    }

    MyVariant& operator=(A&& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(move(a));
        }
        else
        {
            a_ = move(a);
        }
        return *this;
    }

    MyVariant(const B& b)
        : kind_(Kind::B), b_(b)
    {
    }

    MyVariant(B&& b)
        : kind_(Kind::B), b_(move(b))
    {
    }

    MyVariant& operator=(const B& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(b);
        }
        else
        {
            b_ = b;
        }
        return *this;
    }

    MyVariant& operator=(B&& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(move(b));
        }
        else
        {
            b_ = move(b);
        }
        return *this;
    }

    MyVariant(int i)
        : kind_(Kind::Integer), i_(i)
    {
    }

    MyVariant& operator=(int i)
    {
        if (kind_ != Kind::Integer)
        {
            this->~MyVariant();
            new (this) MyVariant(i);
        }
        else
        {
            i_ = i;
        }
        return *this;
    }

    Kind GetKind() const
    {
        return kind_;
    }

    A& GetA()
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    const A& GetA() const
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    B& GetB()
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    const B& GetB() const
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    int& GetInteger()
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

    const int& GetInteger() const
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

private:
    Kind kind_;
    union
    {
        A a_;
        B b_;
        int i_;
    };
};
#pragma warning (pop)

int main()
{
    A a(1, "Hello from A");
    B b(2, "Hello from B");

    MyVariant mv_1 = a;

    cout << "mv_1 = a: " << mv_1.GetA().name << endl;
    mv_1 = b;
    cout << "mv_1 = b: " << mv_1.GetB().name << endl;
    mv_1 = A(3, "hello again from A");
    cout << R"aaa(mv_1 = A(3, "hello again from A"): )aaa" << mv_1.GetA().name << endl;
    mv_1 = 42;
    cout << "mv_1 = 42: " << mv_1.GetInteger() << endl;

    b.vec = { 10,20,30,40,50 };

    mv_1 = move(b);
    cout << "After move, mv_1 = b: vec.size = " << mv_1.GetB().vec.size() << endl;

    cout << endl << "Press a letter" << endl;
    char c;
    cin >> c;
}
```

は union 参照を格納できません。 は、 union 継承もサポートしていません。 つまり、を union ベースとして使用し class たり、別のから継承したり、仮想関数を使用したりすることはできません class 。

## <a name="initialize-a-no-locunion"></a> を初期化しますunion

union中かっこで囲まれた式を割り当てることにより、同じステートメントでを宣言して初期化することができます。 式が評価され、の最初のフィールドに割り当てられ union ます。

```cpp
#include <iostream>
using namespace std;

union NumericType
{
    short       iValue;
    long        lValue;
    double      dValue;
};

int main()
{
    union NumericType Values = { 10 };   // iValue = 10
    cout << Values.iValue << endl;
    Values.dValue = 3.1416;
    cout << Values.dValue << endl;
}
/* Output:
10
3.141600
*/
```

は、 `NumericType` union 次の図に示すように、メモリに配置されます (概念的には)。

![数値型のデータの格納::: no loc (union):::](../cpp/media/vc38ul1.png "NumericType::: no loc (union)::: のデータの格納") <br/>
で `NumericType` のデータの格納 union

## <a name="anonymous-no-locunion"></a><a name="anonymous_unions"></a> 非同期 union

匿名 union は、またはを使用せずに宣言されてい *`class-name`* *`declarator-list`* ます。

> **`union  {`**  *`member-list`*  **`}`**

匿名で宣言された名前 union は、非メンバー変数のように直接使用されます。 これは、匿名で宣言された名前が、 union 外側のスコープ内で一意である必要があることを意味します。

匿名の場合、次の union 追加の制限が適用されます。

- ファイルまたは名前空間スコープで宣言されている場合は、としても宣言する必要があり **`static`** ます。

- メンバーのみを持つことができ **`public`** ます。 **`private`** **`protected`** 匿名のとのメンバーによって union エラーが生成されます。

- メンバー関数を持つことはできません。

## <a name="see-also"></a>関連項目

[クラスと構造体](../cpp/classes-and-structs-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[`class`](../cpp/class-cpp.md)<br/>
[`struct`](../cpp/struct-cpp.md)
