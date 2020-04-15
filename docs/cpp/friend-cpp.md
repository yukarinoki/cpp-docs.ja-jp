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
ms.openlocfilehash: 20116674feffaa5b4bbddf707dd3a4d0c1d9ad98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364441"
---
# <a name="friend-c"></a>friend (C++)

状況によっては、クラスのメンバーではない関数や、別のクラスのすべてのメンバーに対して、メンバーレベルのアクセスを許可する方が便利な場合があります。 クラスの実装側が自分のフレンドを宣言することだけが可能です。 関数またはクラスが自分自身をいずれかのクラスのフレンドとして宣言することはできません。 クラス定義では **、friend**キーワードと非メンバー関数またはその他のクラスの名前を使用して、クラスのプライベートメンバーおよびプロテクト メンバーへのアクセス権を付与します。 テンプレート定義では、型パラメーターをフレンドとして宣言できます。

## <a name="syntax"></a>構文

```
class friend F
friend F;
```

## <a name="friend-declarations"></a>フレンド宣言

以前に宣言されなかったフレンド関数を宣言すると、その関数は外側の非クラス スコープにエクスポートされます。

フレンド宣言で宣言された関数は **、extern**キーワードを使用して宣言された関数として扱われます。 詳細については、「 [extern](extern-cpp.md)」を参照してください。

グローバル スコープの関数はプロトタイプの前にフレンドとして宣言できますが、メンバー関数は、完全なクラス宣言の前にフレンドとして宣言することはできません。 次のコードは、なぜこれが失敗するかを示します。

```cpp
class ForwardDeclared;   // Class name is known.
class HasFriends
{
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected
};
```

前の例では、スコープにクラス名 `ForwardDeclared` を入力しますが、宣言全体、特に関数 `IsAFriend` を宣言する部分は不明です。 したがって、クラス**friend**`HasFriends`内のフレンド宣言はエラーを生成します。

C++11 以降では、クラスのフレンド宣言には 2 つの形式があります。

```cpp
friend class F;
friend F;
```

最初の形式では、その名前の既存のクラスが最も内側の名前空間に見つからなかった場合、新しいクラス F が導入されます。 **C++11**: 2 番目の形式では新しいクラスは導入されません。クラスが既に宣言されている場合に使用でき、テンプレート型パラメーターまたは typedef をフレンドとして宣言するときに使用する必要があります。

参照`class friend F`される型がまだ宣言されていない場合に使用します。

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

次の例では、NS`friend F`の`F`スコープ外で宣言されているクラスを参照します。

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

テンプレート`friend F`パラメータをフレンドとして宣言するために使用します。

```cpp
template <typename T>
class my_class
{
    friend T;
    //...
};
```

typedef をフレンドとして宣言するために使用`friend F`します。

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

**フレンド**関数は、クラスのメンバーではないが、クラスのプライベートメンバーとプロテクトメンバーにアクセスできる関数です。 friend 関数はクラス メンバーと見なされません。これらの関数は、特別なアクセス特権が付与されている標準の外部関数です。 フレンドはクラスのスコープ内にないため、メンバ選択演算子 (**.** -**>**) が別のクラスのメンバーでない場合 **フレンド**関数は、アクセスを許可しているクラスによって宣言されます。 **フレンド**宣言は、クラス宣言の任意の場所に配置できます。 アクセス制御キーワードによる影響はありません。

次に、`Point` クラスと `ChangePrivate` フレンド関数の例を示します。 **friend**関数は、パラメーターとして受け取ったオブジェクト`Point`のプライベート データ メンバーにアクセスできます。

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

この例では、`A::Func1( B& )` 関数に `B` クラスへのフレンド アクセスのみ許可されます。 したがって、プライベート`_b`メンバへのアクセスはクラス`Func1``A`では正しいが、`Func2`では正しくない。

`friend` クラスは、すべてのメンバー関数が、クラスのその他のプライベート メンバーとプロテクト メンバーにアクセスできるメンバー関数を持つ、クラスのフレンド関数であるクラスです。 `friend` クラスの `B` 宣言が次のようになっていたとします。

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

マネージ型 (C++/CLI) には、フレンド関数、フレンド クラス、またはフレンド インターフェイスを持つことはできません。

フレンド関係は継承されません。つまり、`YourOtherClass` から派生したクラスは `YourClass` のプライベート メンバーにアクセスできません。 フレンド関係は推移的ではないため、`YourOtherClass` のフレンドであるクラスは `YourClass` にアクセスできません。

次の図は、4 つのクラス宣言 (`Base`、`Derived`、`aFriend`、`anotherFriend`) を示しています。 `aFriend` のプライベート メンバー (および `Base` が継承した可能性があるすべてのメンバー) に直接アクセスできるのは、`Base` クラスだけです。

![フレンド関係の包含](../cpp/media/vc38v41.gif "フレンド関係の包含") <br/>
フレンド関係の包含

## <a name="inline-friend-definitions"></a>インラインのフレンドの定義

フレンド関数はクラス宣言の内部で (関数本体を与えられた) 定義できます。 これらの関数はインライン関数であり、メンバーのインライン関数のように、すべてのクラス メンバーが発生した直後、クラス スコープが閉じる前に定義されているように動作します (クラス宣言の末尾)。 クラス宣言の内部で定義されているフレンド関数は、外側のクラスのスコープ内にあります。

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)
