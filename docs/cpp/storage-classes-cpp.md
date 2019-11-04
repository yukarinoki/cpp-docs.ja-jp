---
title: ストレージ クラス (C++)
ms.date: 11/04/2016
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: 92435b2bab670dd366f26c981443e98e4a4e3c29
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221985"
---
# <a name="storage-classes-c"></a>ストレージ クラス (C++)

A*ストレージ クラス*C++ のコンテキストでの変数宣言は、オブジェクトの有効期間、リンケージ、およびメモリの場所を制御する型指定子。 特定のオブジェクトはストレージ クラスを 1 つのみ持つことができます。 それ以外の場合を使用して指定されていない場合、ブロック内で定義されている変数は自動ストレージを持ちます、 **extern**、**静的**、または`thread_local`指定子。 自動オブジェクトおよび変数にはリンケージがないため、ブロックの外側のコードには不可視です。

**ノート**

1. [変更可能な](../cpp/mutable-data-members-cpp.md)キーワードが、ストレージ クラス指定子として見なされます。 ただし、クラス定義のメンバー一覧でのみ使用できます。

1. **Visual Studio 2010 以降の場合:** **自動**キーワードは C++ ストレージ クラス指定子では不要になったと**登録**キーワードは非推奨とされます。 **Visual Studio 2017 バージョン 15.7 以降:** (で使用可能な[/std:c++ 17](../build/reference/std-specify-language-standard-version.md))。**登録**キーワードは C++ 言語から削除されます。

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>このセクションの内容:

- [static](#static)
- [extern](#extern)
- [thread_local](#thread_local)

## <a name="static"></a> 静的

**静的**キーワードを使用して、変数やグローバル スコープ、名前空間スコープ、およびクラス スコープで関数を宣言することができます。 静的変数は、ローカル スコープでも宣言できます。

静的存続期間は、オブジェクトまたは変数がプログラム起動時に割り当てられ、プログラムの終了時に解放されることを意味します。 外部リンケージは、変数が宣言されたファイルの外部から変数名が参照できることを意味します。 逆に、内部リンケージは、変数が宣言されたファイルの外部でその名前を参照できないことを意味します。 既定では、グローバル名前空間で定義されたオブジェクトまたは変数には静的存続期間と外部リンケージがあります。 **静的**キーワードは、次の状況で使用することができます。

1. 変数またはファイルのスコープで関数を宣言する場合 (グローバルまたは名前空間スコープ)、**静的**キーワードは、変数または関数が、内部リンケージを持つことを指定します。 変数を宣言すると、変数は静的存続期間が設定され、コンパイラによって 0 に初期化されます (別の値を指定していない場合)。

1. 関数で変数を宣言するときに、**静的**キーワードは、変数がその関数呼び出しの間には、その状態を保持することを指定します。

1. クラス宣言でのデータ メンバーを宣言するときに、**静的**キーワードは、メンバーの 1 つのコピーが、クラスのすべてのインスタンスで共有されることを指定します。 静的データ メンバーはファイル スコープで定義する必要があります。 整数データ メンバーとして宣言する**const 静的**初期化子を持つことができます。

1. クラス宣言でメンバー関数を宣言するときに、**静的**キーワードは、関数がクラスのすべてのインスタンスで共有されることを指定します。 静的メンバー関数は、関数は、暗黙の型があるないために、インスタンス メンバーにアクセスできません**この**ポインター。 インスタンス メンバーにアクセスするには、インスタンスのポインターまたは参照であるパラメーターを受け取る関数を宣言します。

1. 共用体のメンバーを static として宣言することはできません。 グローバルに宣言された匿名共用体に明示的に宣言する必要がありますが、**静的**します。

この例では、変数の宣言方法**静的**関数でその関数呼び出しの間には、その状態を保持します。

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

この例の使用を示しています。**静的**クラスでします。

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

この例で宣言されたローカル変数**静的**メンバー関数。 静的変数は、プログラム全体で使用できます。型のすべてのインスタンスは、静的変数の同じコピーを共有します。

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

C++11 以降では、静的ローカル変数の初期化はスレッド セーフであることが保証されています。 この機能が呼ば*マジック スタティック*します。 ただし、マルチスレッド アプリケーションでは、後続の割り当てはすべて同期する必要があります。 使用して、スレッド セーフな静的な初期化の機能を無効にすることができます、 [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) CRT に依存することを回避するフラグ。

## <a name="extern"></a> extern

オブジェクトおよび変数として宣言されている**extern**別の翻訳単位または外側のスコープ外部リンケージを持つものとして定義されているオブジェクトを宣言します。

宣言**const**で変数を**extern**ストレージ クラスが外部リンケージを持つ変数を強制します。 初期化、 **extern const**変数が定義する翻訳単位で許可されています。 定義している翻訳単位以外の翻訳単位の初期化は未定義の結果になります。 詳細については、次を参照してください[extern リンケージの指定を使用した。](../cpp/using-extern-to-specify-linkage.md)

[/Zc: externconstexpr](../build/reference/zc-externconstexpr.md)コンパイラ オプションは、適用するコンパイラ[外部リンケージ](../c-language/external-linkage.md)を使用して宣言された変数に`extern constexpr`します。 以前のバージョンの Visual Studio で、既定の場合、または **/Zc:externConstexpr-** を指定すると、Visual Studio に内部リンケージを適用する**constexpr**変数場合でも、 **extern**キーワードを使用します。 **/Zc: externconstexpr**オプションは、Visual Studio 2017 Update 15.6 以降を使用します。 既定で無効であるとします。 促す/permissive-オプションには、/zc: externconstexpr が有効にしません。

次のコードは 2 つ**extern**宣言、 `DefinedElsewhere` (これは別の翻訳単位で定義された名前を参照) と`DefinedHere`(これは外側のスコープで定義された名前を参照)。

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

`thread_local` 指定子で宣言された変数は、それが作成されたスレッドでのみアクセスできます。 変数は、スレッドが作成されるときに作成され、スレッドが破棄されるときに破棄されます。 各スレッドには、それ自体の変数のコピーがあります。 Windows で`thread_local`は機能的には、Microsoft 固有[_ _declspec (thread)](../cpp/thread.md)属性。

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

について注意すべき点、`thread_local`指定子。

- すべての呼び出し元スレッドを Dll に動的に初期化されたスレッド ローカル変数が正しく初期化されていません可能性があります。 詳細については、[スレッド](thread.md) に関するページを参照してください。

- `thread_local`指定子と組み合わせることがあります**静的**または**extern**します。

- 適用できる`thread_local`のみにデータの宣言と定義されます。`thread_local`関数宣言または定義では使用できません。

- `thread_local` は、静的ストレージ存続期間のあるデータ項目にのみ指定できます。 これには、グローバルなデータ オブジェクトが含まれます (どちらも**静的**と**extern**)、ローカルな静的オブジェクト、およびクラスの静的データ メンバー。 任意のローカル変数が宣言されている`thread_local`は他のストレージ クラスが提供されていない場合は、暗黙的に静的つまり、ブロック スコープで`thread_local`と等価`thread_local static`します。

- 宣言と定義が同じファイルと別々のファイルのどちらで発生する場合でも、スレッド ローカル オブジェクトの宣言と定義には `thread_local` を使用する必要があります。

Windows で`thread_local`は機能的に等価[_declspec](../cpp/thread.md)する点を除いて **_declspec**型定義に適用できるし、C コードでは無効です。 `thread_local` は C++ 標準の一部であり、移植性がより高いため、できるだけ常にこれを使用してください。

##  <a name="register"></a>  register

**Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c++ 17](../build/reference/std-specify-language-standard-version.md))。**登録**キーワードがサポートされているストレージ クラスではなくなりました。 キーワードは、将来使用するための標準でまだ予約されています。

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>例: 自動の静的な初期化との比較

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

この例は、方法とタイミングを示しますオブジェクト`I1`、`I2`と`I3`初期化されますが破棄されるとします。

プログラムに関する注意事項をいくつかの点があります。

- 最初に、制御フローが `I1` と `I2` を定義しているブロックを終了すると、これらは自動的に破棄されます。

- 次に、C++ では、ブロックの先頭でオブジェクトや変数を宣言する必要はありません。 さらに、これらのオブジェクトは、制御フローが定義に到達した場合にのみ初期化されます (このような定義には、`I2` や `I3` などがあります)。出力は、これらがいつ初期化されるかを正確に示します。

- 最後に、`I3` などの静的ローカル変数は、プログラム実行中は値が保持されますが、プログラムが終了すると破棄されます。

## <a name="see-also"></a>関連項目

[宣言と定義](../cpp/declarations-and-definitions-cpp.md)