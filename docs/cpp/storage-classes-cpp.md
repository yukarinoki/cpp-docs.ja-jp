---
title: ストレージ クラス (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
- register_cpp
dev_langs:
- C++
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a56d456564dc171292e8a58b6cb486ce2dfbaf31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32424590"
---
# <a name="storage-classes-c"></a>ストレージ クラス (C++)  
  
A*ストレージ クラス*変数宣言は型指定子オブジェクトの有効期間、リンケージ、およびメモリの場所を制御する、C++ のコンテキストでします。 特定のオブジェクトはストレージ クラスを 1 つのみ持つことができます。 ブロック内で定義された変数は、`extern`、`static`、または `thread_local` 指定子によって指定されていない限り、自動ストレージを持ちます。 自動オブジェクトおよび変数にはリンケージがないため、ブロックの外側のコードには不可視です。  
  
**ノート**  
  
1.  [変更可能な](../cpp/mutable-data-members-cpp.md)キーワードと思われるストレージ クラス指定子。 ただし、クラス定義のメンバー一覧でのみ使用できます。  
  
2.  **Visual C 2010 以降:** 、`auto`キーワードは、C++ ストレージ クラス指定子では不要になったと`register`キーワードは推奨されなくなりました。 **Visual Studio 2017 15.7 およびそれ以降のバージョン:** (で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):`register`キーワードは C++ 言語から削除します。


```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>このセクションの内容:

- [static](#static)
- [extern](#extern)
- [thread_local](#thread_local)

## <a name="static"></a> 静的

`static` キーワードを使用すると、変数と関数をグローバル スコープ、名前空間スコープ、およびクラス スコープで宣言することができます。 静的変数は、ローカル スコープでも宣言できます。

静的存続期間は、オブジェクトまたは変数がプログラム起動時に割り当てられ、プログラムの終了時に解放されることを意味します。 外部リンケージは、変数が宣言されたファイルの外部から変数名が参照できることを意味します。 逆に、内部リンケージは、変数が宣言されたファイルの外部でその名前を参照できないことを意味します。 既定では、グローバル名前空間で定義されたオブジェクトまたは変数には静的存続期間と外部リンケージがあります。 キーワード `static` は次の状況で使用できます。

1. ファイル スコープ (グローバル スコープまたは名前空間スコープ、あるいはその両方) で変数または関数を宣言する場合、`static` キーワードは、変数または関数に内部リンケージがあることを指定します。 変数を宣言すると、変数は静的存続期間が設定され、コンパイラによって 0 に初期化されます (別の値を指定していない場合)。

1. 関数で変数を宣言する場合、`static` キーワードは、その関数の呼び出しと呼び出しの間に変数がその状態を保持することを指定します。

1. クラス宣言でデータ メンバーを宣言する場合、`static` キーワードは、メンバーの 1 つのコピーがクラスのすべてのインスタンスで共有されることを指定します。 静的データ メンバーはファイル スコープで定義する必要があります。 整数データ メンバーとして宣言する`const static`初期化子を持つことができます。

1. クラス宣言でメンバー関数を宣言する場合、`static` キーワードは、関数がクラスのすべてのインスタンスで共有されることを指定します。 静的メンバー関数は、関数に暗黙の `this` ポインターがないため、インスタンス メンバーにアクセスできません。 インスタンス メンバーにアクセスするには、インスタンスのポインターまたは参照であるパラメーターを受け取る関数を宣言します。

1. 共用体のメンバーを static として宣言することはできません。 ただし、グローバルに宣言された匿名共用体は、明示的に `static` として宣言する必要があります。

この例では、変数の宣言方法`static`関数で、その関数呼び出しの間には、その状態を保持します。

```cpp
// static1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void showstat( int curr ) {
   static int nStatic;    // Value of nStatic is retained
                          // between each function call
   nStatic += curr;
   cout << "nStatic is " << nStatic << endl;
}

int main() {
   for ( int i = 0; i < 5; i++ )
      showstat( i );
}
```

```Output
nStatic is 0
nStatic is 1
nStatic is 3
nStatic is 6
nStatic is 10
```

この例に示しますの`static`クラスでします。

```cpp
// static2.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CMyClass {
public:
   static int m_i;
};

int CMyClass::m_i = 0;
CMyClass myObject1;
CMyClass myObject2;

int main() {
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject1.m_i = 1;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject2.m_i = 2;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   CMyClass::m_i = 3;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;
}
```

```Output
0
0
1
1
2
2
3
3
```

この例で宣言されたローカル変数`static`メンバー関数。 静的変数は、プログラム全体で使用できます。型のすべてのインスタンスは、静的変数の同じコピーを共有します。

```cpp
// static3.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
struct C {
   void Test(int value) {
      static int var = 0;
      if (var == value) 
         cout << "var == value" << endl;
      else
         cout << "var != value" << endl;

      var = value;
   }
}; 

int main() {
   C c1;
   C c2;
   c1.Test(100);
   c2.Test(100);
}
```

```Output
var != value
var == value
```

C++11 以降では、静的ローカル変数の初期化はスレッド セーフであることが保証されています。 この機能と呼ぶことが*静的マジック*です。 ただし、マルチスレッド アプリケーションでは、後続の割り当てはすべて同期する必要があります。 使用して、スレッド セーフな静的初期化機能を無効にすることができます、 [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) CRT の依存関係を防ぐためにフラグ。

## <a name="extern"></a> extern

`extern` として宣言されたオブジェクトと変数は、別の翻訳単位または外側のスコープで定義されているオブジェクトを、外部リンケージを持つものとして宣言します。

宣言`const`を持つ変数、`extern`ストレージ クラスが外部リンケージを持つ変数を強制します。 初期化、`extern const`定義の翻訳単位で変数を使用します。 定義している翻訳単位以外の翻訳単位の初期化は未定義の結果になります。 詳細については、次を参照してください[extern リンケージの指定を使用した。](../cpp/using-extern-to-specify-linkage.md)

[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)コンパイラ オプションは、適用するコンパイラ[外部リンケージ]()を使用して宣言される変数に**extern constexpr**です。 以前のバージョンの Visual Studio で、既定の場合、または **/Zc:externConstexpr-** を指定すると、Visual Studio に内部リンケージを適用する**constexpr**変数場合であっても、 **extern**キーワードを使用します。 **/Zc:externConstexpr**オプションは、Visual Studio 2017 更新 15.6 以降を使用します。 既定では無効になっているとします。 /Permissive-option に/Zc:externConstexpr が有効にできません。

次のコードは、2 つの `extern` 宣言、`DefinedElsewhere` (別の翻訳単位で定義された名前を参照する) と `DefinedHere` (外側のスコープで定義された名前を参照する) を示しています。

```cpp
// external.cpp
// DefinedElsewhere is defined in another translation unit
extern int DefinedElsewhere;   
int main() {
   int DefinedHere; 
   {
      // refers to DefinedHere in the enclosing scope
      extern int DefinedHere;
   }
}
```

## <a name="thread_local"></a> thread_local (c++ 11)

`thread_local` 指定子で宣言された変数は、それが作成されたスレッドでのみアクセスできます。 変数は、スレッドが作成されるときに作成され、スレッドが破棄されるときに破棄されます。 各スレッドには、それ自体の変数のコピーがあります。 Windows では、`thread_local`は機能的には、Microsoft 固有[_ _declspec (thread)](../cpp/thread.md)属性。

```cpp
thread_local float f = 42.0; // Global namespace. Not implicitly static.

struct S // cannot be applied to type definition
{
    thread_local int i; // Illegal. The member must be static.
    thread_local static char buf[10]; // OK 
};

void DoSomething()
{
    // Apply thread_local to a local variable.
    // Implicitly "thread_local static S my_struct".
    thread_local S my_struct;
}
```

注意点、`thread_local`指定子。

- すべての呼び出し元スレッドに Dll で動的に初期化されたスレッド ローカル変数が正しく初期化されていません可能性があります。 詳細については、[スレッド](thread.md) に関するページを参照してください。

-  `thread_local`指定子と組み合わせることがあります`static`または`extern`です。

-  適用できる`thread_local`のみにデータの宣言と定義されます。`thread_local`関数宣言または定義では使用できません。

-  `thread_local` は、静的ストレージ存続期間のあるデータ項目にのみ指定できます。 これには、グローバルなデータ オブジェクトが含まれます (両方`static`と`extern`)、ローカルな静的オブジェクト、およびクラスの静的データ メンバーです。 任意のローカル変数が宣言されている`thread_local`が他のストレージ クラスが提供されていない場合、暗黙的に静的ではブロック スコープ、つまり、`thread_local`と等価`thread_local static`です。 

-  宣言と定義が同じファイルと別々のファイルのどちらで発生する場合でも、スレッド ローカル オブジェクトの宣言と定義には `thread_local` を使用する必要があります。

Windows では、`thread_local`は機能的に等価[_declspec](../cpp/thread.md)する点を除いて`__declspec(thread)`型定義に適用できます。 C コードでは有効では、とします。 `thread_local` は C++ 標準の一部であり、移植性がより高いため、できるだけ常にこれを使用してください。

##  <a name="register"></a>  register

**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):`register`キーワードがサポートされているストレージ クラスではなくなりました。 キーワードは、将来使用する規格でまだ予約されています。 

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>例: 自動静的な初期化との比較

ローカル自動オブジェクトまたは変数が、制御フローが定義に到達するたびに初期化されます。 ローカル静的オブジェクトまたは変数が、最初に制御フローが定義に到達すると初期化されます。

オブジェクトの初期化と破棄をログに記録するクラスを定義し、`I1`、`I2`、および `I3` の 3 つのオブジェクトを定義する、次の例を考えます。

```cpp
// initialization_of_objects.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>
using namespace std;

// Define a class that logs initializations and destructions.
class InitDemo {
public:
    InitDemo( const char *szWhat );
    ~InitDemo();

private:
    char *szObjName;
    size_t sizeofObjName;
};

// Constructor for class InitDemo
InitDemo::InitDemo( const char *szWhat ) :
    szObjName(NULL), sizeofObjName(0) {
    if ( szWhat != 0 && strlen( szWhat ) > 0 ) {
        // Allocate storage for szObjName, then copy
        // initializer szWhat into szObjName, using
        // secured CRT functions.
        sizeofObjName = strlen( szWhat ) + 1;

        szObjName = new char[ sizeofObjName ];
        strcpy_s( szObjName, sizeofObjName, szWhat );

        cout << "Initializing: " << szObjName << "\n";
    }
    else {
        szObjName = 0;
    }
}

// Destructor for InitDemo
InitDemo::~InitDemo() {
    if( szObjName != 0 ) {
        cout << "Destroying: " << szObjName << "\n";
        delete szObjName;
    }
}

// Enter main function
int main() {
    InitDemo I1( "Auto I1" ); {
        cout << "In block.\n";
        InitDemo I2( "Auto I2" );
        static InitDemo I3( "Static I3" );
    }
    cout << "Exited block.\n";
}
```

```Output
Initializing: Auto I1
In block.
Initializing: Auto I2
Initializing: Static I3
Destroying: Auto I2
Exited block.
Destroying: Auto I1
Destroying: Static I3
```

この例は、時期と方法を示しています。 オブジェクト`I1`、 `I2`、および`I3`初期化されますが破棄されるとします。

プログラムについての注意事項をいくつかの点があります。

- 最初に、制御フローが `I1` と `I2` を定義しているブロックを終了すると、これらは自動的に破棄されます。

- 次に、C++ では、ブロックの先頭でオブジェクトや変数を宣言する必要はありません。 さらに、これらのオブジェクトは、制御フローが定義に到達した場合にのみ初期化されます  (このような定義には、`I2` や `I3` などがあります)。出力は、これらがいつ初期化されるかを正確に示します。

- 最後に、`I3` などの静的ローカル変数は、プログラム実行中は値が保持されますが、プログラムが終了すると破棄されます。

## <a name="see-also"></a>関連項目

 [宣言と定義](../cpp/declarations-and-definitions-cpp.md)
