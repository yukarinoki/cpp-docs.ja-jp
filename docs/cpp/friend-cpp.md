---
title: フレンド (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- friend_cpp
dev_langs:
- C++
helpviewer_keywords:
- member access, from friend functions
- friend classes [C++]
- friend keyword [C++]
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1538ad67ce1b742c55dc413d78e40e8dcc9884df
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418264"
---
# <a name="friend-c"></a>friend (C++)
状況によっては、クラスのメンバーではない関数またはすべてのメンバーが別のクラスにメンバー レベルのアクセスを許可する方が便利です。 クラスの実装側が自分のフレンドを宣言することだけが可能です。 関数またはクラスが自分自身をいずれかのクラスのフレンドとして宣言することはできません。 クラスの定義で使用して、`friend`キーワードと、非メンバー関数またはクラスのプライベートおよびプロテクト メンバーへのアクセスを許可するには、他のクラスの名前。         テンプレートの定義に型パラメーターは、フレンドとして宣言できます。  
  
## <a name="syntax"></a>構文  
  
```  
class friend F  
friend F;  
```  
  
## <a name="friend-declarations"></a>フレンド宣言  
 以前に宣言されなかったフレンド関数を宣言すると、その関数は外側の非クラス スコープにエクスポートされます。  
  
 フレンド宣言で宣言された関数は、`extern` キーワードを使って宣言されたものとして扱われます  (詳細については`extern`を参照してください[静的ストレージ クラス指定子](http://msdn.microsoft.com/en-us/3ba9289a-a412-4a17-b319-ceb2c087df48))。  
  
 グローバル スコープの関数はプロトタイプの前にフレンドとして宣言できますが、メンバー関数は、完全なクラス宣言の前にフレンドとして宣言することはできません。 次のコードは、なぜこれが失敗するかを示します。  
  
```cpp  
class ForwardDeclared;   // Class name is known.  
class HasFriends  
{  
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected  
};  
```  
  
 前の例では、スコープにクラス名 `ForwardDeclared` を入力しますが、宣言全体、特に関数 `IsAFriend` を宣言する部分は不明です。 したがって、`friend` クラスの `HasFriends` 宣言はエラーを生成します。  
  
 クラスのフレンド宣言の 2 つの形式が、c++ 11 以降です。  
  
```cpp  
friend class F;  
friend F;  
```  
  
 最初の形式では、最も内側の名前空間にその名前の既存のクラスが見つからなかった場合、新しいクラス F が導入されています。  **C++ 11**: 2 番目の形式は、新しいクラスを導入していません。 クラスは、既に宣言されている、およびテンプレート型パラメーターまたはフレンドとしての typedef を宣言するときに使用する必要があるときに使用できます。  
  
 使用する`class friend F`と参照先の型はまだ宣言されていません。  
  
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
  
 次の例では、`friend F`を指す、 `F` NS のスコープ外宣言されているクラスです。  
  
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
  
 使用して`friend F`フレンドとしてテンプレート パラメーターを宣言します。  
  
```cpp  
template <typename T>  
class my_class  
{  
    friend T;  
    //...  
};  
```  
  
 使用して`friend F`フレンドとしての typedef を宣言します。  
  
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
>  2 番目のクラス全体は最初のクラスへのフレンドである必要がありますが、最初のクラスのどの関数が 2 番目のクラスのフレンドであるかを選択できます。  
  
## <a name="friend-functions"></a>friend 関数  
 `friend` 関数は、クラスのメンバーではないが、クラスのプライベート メンバーとプロテクト メンバーにアクセスできる関数です。 friend 関数はクラス メンバーと見なされません。これらの関数は、特別なアクセス特権が付与されている標準の外部関数です。 友人は、クラスのスコープに含まれないし、メンバー選択演算子を使用して呼び出されません (**です。** パラメーターと**>**) 別のクラスのメンバーでない限り、します。 `friend` 関数はアクセスを付与しているクラスで宣言されます。 `friend` 宣言はクラス宣言内の任意の場所に配置できます。 アクセス制御キーワードによる影響はありません。  
  
 次に、`Point` クラスと `ChangePrivate` フレンド関数の例を示します。 この `friend` 関数は、自身がパラメーターとして受け取る `Point` オブジェクトのプライベート データ メンバーにアクセスできます。  
  
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
 クラス メンバー関数は他のクラスのフレンドとして宣言できます。 次に例を示します。  
  
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
  
 この例では、`A::Func1( B& )` 関数に `B` クラスへのフレンド アクセスのみ許可されます。 つまり、プライベート メンバーにアクセス`_b`で正しい`Func1`クラスの`A`ではなく`Func2`です。  
  
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
  
 マネージ型に、フレンド関数、フレンド クラス、またはフレンド インターフェイスを含めることはできません。  
  
 フレンド関係は継承されません。つまり、`YourOtherClass` から派生したクラスは `YourClass` のプライベート メンバーにアクセスできません。 フレンド関係は推移的ではないため、`YourOtherClass` のフレンドであるクラスは `YourClass` にアクセスできません。  
  
 次の図は、4 つのクラス宣言 (`Base`、`Derived`、`aFriend`、`anotherFriend`) を示しています。 `aFriend` のプライベート メンバー (および `Base` が継承した可能性があるすべてのメンバー) に直接アクセスできるのは、`Base` クラスだけです。  
  
 ![フレンド関係の包含](../cpp/media/vc38v41.gif "vc38V41")  
フレンド関係の包含  
  
## <a name="inline-friend-definitions"></a>インラインのフレンドの定義  
 friend 関数は、クラス宣言内で定義できます。 これらの関数はインライン関数であり、メンバーのインライン関数のように、すべてのクラス メンバーが発生した直後、クラス スコープが閉じる前に定義されているように動作します (クラス宣言の末尾)。  
  
 クラス宣言内で定義された friend 関数は、それを囲んでいるクラスのスコープ内にあるとは見なされません。それらはファイル スコープ内にあると見なされます。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)