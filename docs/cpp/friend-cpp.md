---
title: friend (C++)
ms.date: 07/15/2019
f1_keywords:
- friend_cpp
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
ms.openlocfilehash: 772eada8257917a6127b15ea2e50946aebb3bc74
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227466"
---
# <a name="friend-c"></a>friend (C++)

場合によっては、クラスのメンバーではない関数、または別のクラスのすべてのメンバーではない関数に、メンバーレベルのアクセスを許可する方が便利です。 クラスの実装側が自分のフレンドを宣言することだけが可能です。 関数またはクラスが自分自身をいずれかのクラスのフレンドとして宣言することはできません。 クラス定義では、 **`friend`** キーワードと非メンバー関数またはその他のクラスの名前を使用して、クラスのプライベートメンバーとプロテクトメンバーへのアクセスを許可します。 テンプレート定義では、型パラメーターを friend として宣言できます。

## <a name="syntax"></a>構文

```
class friend F
friend F;
```

## <a name="friend-declarations"></a>フレンド宣言

以前に宣言されなかったフレンド関数を宣言すると、その関数は外側の非クラス スコープにエクスポートされます。

Friend 宣言で宣言された関数は、キーワードを使用して宣言されているかのように扱われ **`extern`** ます。 詳細については、「 [extern](extern-cpp.md)」を参照してください。

グローバル スコープの関数はプロトタイプの前にフレンドとして宣言できますが、メンバー関数は、完全なクラス宣言の前にフレンドとして宣言することはできません。 次のコードは、なぜこれが失敗するかを示します。

```cpp
class ForwardDeclared;   // Class name is known.
class HasFriends
{
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected
};
```

前の例では、スコープにクラス名 `ForwardDeclared` を入力しますが、宣言全体、特に関数 `IsAFriend` を宣言する部分は不明です。 したがって、 **`friend`** クラスの宣言によって `HasFriends` エラーが生成されます。

C++ 11 以降では、クラスのフレンド宣言には次の2つの形式があります。

```cpp
friend class F;
friend F;
```

最初のフォームでは、その名前の既存のクラスが最も内側の名前空間に見つからなかった場合に、新しいクラス F が導入されます。 **C++ 11**: 2 番目の形式では新しいクラスは導入されません。このクラスは、クラスが既に宣言されている場合に使用でき、テンプレート型パラメーターまたは typedef をフレンドとして宣言するときに使用する必要があります。

`class friend F`参照型がまだ宣言されていない場合は、を使用します。

```cpp
namespace NS
{
    class M
    {
        class friend F;  // Introduces F but doesn't define it
    };
}
```

```cpp
namespace NS
{
    class M
    {
        friend F; // error C2433: 'NS::F': 'friend' not permitted on data declarations
    };
}
```

次の例では、が `friend F` `F` NS のスコープ外で宣言されているクラスを参照しています。

```cpp
class F {};
namespace NS
{
    class M
    {
        friend F;  // OK
    };
}
```

を使用し `friend F` て、テンプレートパラメーターをフレンドとして宣言します。

```cpp
template <typename T>
class my_class
{
    friend T;
    //...
};
```

を使用し `friend F` て、typedef を friend として宣言します。

```cpp
class Foo {};
typedef Foo F;

class G
{
    friend F; // OK
    friend class F // Error C2371 -- redefinition
};
```

相互にフレンドである 2 つのクラスを宣言するには、2 番目のクラス全体が最初のクラスのフレンドとして指定される必要があります。 この制限の理由は、2 番目のクラスが宣言された位置でのみコンパイラは個々のフレンド関数を宣言するために十分な情報を得られるためです。

> [!NOTE]
> 2 番目のクラス全体は最初のクラスへのフレンドである必要がありますが、最初のクラスのどの関数が 2 番目のクラスのフレンドであるかを選択できます。

## <a name="friend-functions"></a>friend 関数

**`friend`** 関数は、クラスのメンバーではなく、クラスのプライベートメンバーとプロテクトメンバーにアクセスできる関数です。 friend 関数はクラス メンバーと見なされません。これらの関数は、特別なアクセス特権が付与されている標準の外部関数です。 フレンドはクラスのスコープに含まれておらず、メンバー選択演算子 () を使用して呼び出されることはありません **。** **>** 他のクラスのメンバーでない場合)。 関数は、 **`friend`** アクセスを許可するクラスによって宣言されます。 **`friend`** 宣言は、クラス宣言内の任意の場所に配置できます。 アクセス制御キーワードによる影響はありません。

次に、`Point` クラスと `ChangePrivate` フレンド関数の例を示します。 関数は、 **`friend`** `Point` パラメーターとして受け取るオブジェクトのプライベートデータメンバーにアクセスできます。

```cpp
// friend_functions.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class Point
{
    friend void ChangePrivate( Point & );
public:
    Point( void ) : m_i(0) {}
    void PrintPrivate( void ){cout << m_i << endl; }

private:
    int m_i;
};

void ChangePrivate ( Point &i ) { i.m_i++; }

int main()
{
   Point sPoint;
   sPoint.PrintPrivate();
   ChangePrivate(sPoint);
   sPoint.PrintPrivate();
// Output: 0
           1
}
```

## <a name="class-members-as-friends"></a>フレンドとしてのクラス メンバー

クラス メンバー関数は他のクラスのフレンドとして宣言できます。 次の例を確認してください。

```cpp
// classes_as_friends1.cpp
// compile with: /c
class B;

class A {
public:
   int Func1( B& b );

private:
   int Func2( B& b );
};

class B {
private:
   int _b;

   // A::Func1 is a friend function to class B
   // so A::Func1 has access to all members of B
   friend int A::Func1( B& );
};

int A::Func1( B& b ) { return b._b; }   // OK
int A::Func2( B& b ) { return b._b; }   // C2248
```

この例では、`A::Func1( B& )` 関数に `B` クラスへのフレンド アクセスのみ許可されます。 したがって、プライベートメンバーへ `_b` のアクセスは、クラスのでは正しいが、では正しくあり `Func1` `A` ません `Func2` 。

**`friend`** クラスは、クラスのフレンド関数であるクラスです。つまり、メンバー関数は、他のクラスのプライベートメンバーとプロテクトメンバーにアクセスできます。 **`friend`** クラスの宣言が `B` 次のようになったとします。

```cpp
friend class A;
```

その場合、`A` クラスのすべてのメンバー関数に `B` クラスへのフレンド アクセスが許可されます。 次に、フレンド クラスの例を示します。

```cpp
// classes_as_friends2.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class YourClass {
friend class YourOtherClass;  // Declare a friend class
public:
   YourClass() : topSecret(0){}
   void printMember() { cout << topSecret << endl; }
private:
   int topSecret;
};

class YourOtherClass {
public:
   void change( YourClass& yc, int x ){yc.topSecret = x;}
};

int main() {
   YourClass yc1;
   YourOtherClass yoc1;
   yc1.printMember();
   yoc1.change( yc1, 5 );
   yc1.printMember();
}
```

明示的に指定されていない限り、フレンド関係は相互関係ではありません。 上の例では、`YourClass` のメンバー関数は `YourOtherClass` のプライベート メンバーにアクセスできません。

マネージ型 (C++/CLI) には、フレンド関数、フレンドクラス、またはフレンドインターフェイスを含めることはできません。

フレンド関係は継承されません。つまり、`YourOtherClass` から派生したクラスは `YourClass` のプライベート メンバーにアクセスできません。 フレンド関係は推移的ではないため、`YourOtherClass` のフレンドであるクラスは `YourClass` にアクセスできません。

次の図は、4 つのクラス宣言 (`Base`、`Derived`、`aFriend`、`anotherFriend`) を示しています。 `aFriend` のプライベート メンバー (および `Base` が継承した可能性があるすべてのメンバー) に直接アクセスできるのは、`Base` クラスだけです。

![フレンド関係の包含](../cpp/media/vc38v41.gif "フレンド関係の包含") <br/>
フレンド関係の包含

## <a name="inline-friend-definitions"></a>インラインのフレンドの定義

フレンド関数は、クラス宣言内で (関数本体を指定して) 定義できます。 これらの関数はインライン関数であり、メンバーのインライン関数のように、すべてのクラス メンバーが発生した直後、クラス スコープが閉じる前に定義されているように動作します (クラス宣言の末尾)。 クラス宣言内で定義されているフレンド関数は、外側のクラスのスコープ内にあります。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
