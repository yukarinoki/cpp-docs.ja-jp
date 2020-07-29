---
title: ストレージ クラス (C++)
description: C++ では、static、extern、および thread_local キーワードによって、変数または関数の有効期間、リンケージ、およびメモリ位置が指定されます。
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: c3fc87980d1fd0af5b803a8e590855f6429c847e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213165"
---
# <a name="storage-classes"></a>ストレージ クラス

C++ 変数宣言のコンテキストにおける*ストレージクラス*は、オブジェクトの有効期間、リンケージ、およびメモリ位置を制御する型指定子です。 特定のオブジェクトはストレージ クラスを 1 つのみ持つことができます。 ブロック内で定義された変数は **`extern`** 、、、または指定子を使用して指定されている場合を除き、自動ストレージを持ち **`static`** **`thread_local`** ます。 自動オブジェクトおよび変数にはリンケージがないため、ブロックの外側のコードには不可視です。 メモリは、ブロックが終了したときにブロックに入って割り当てが解除されると、自動的に割り当てられます。

**ノート**

1. [Mutable](../cpp/mutable-data-members-cpp.md)キーワードは、ストレージクラス指定子と見なすことができます。 ただし、クラス定義のメンバー一覧でのみ使用できます。

1. **Visual Studio 2010 以降:****`auto`** キーワードは C++ のストレージクラス指定子ではなくなりました **`register`** 。キーワードは非推奨とされます。 **Visual Studio 2017 バージョン15.7 以降:** (で使用可能 [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`register`** キーワードは C++ 言語から削除されます。

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a><a name="static"></a> `static`

キーワードを使用すると、 **`static`** グローバルスコープ、名前空間スコープ、およびクラススコープで変数と関数を宣言できます。 静的変数は、ローカル スコープでも宣言できます。

静的存続期間は、オブジェクトまたは変数がプログラム起動時に割り当てられ、プログラムの終了時に解放されることを意味します。 外部リンケージは、変数が宣言されたファイルの外部から変数名が参照できることを意味します。 逆に、内部リンケージは、変数が宣言されたファイルの外部でその名前を参照できないことを意味します。 既定では、グローバル名前空間で定義されたオブジェクトまたは変数には静的存続期間と外部リンケージがあります。 キーワードは、 **`static`** 次のような場合に使用できます。

1. ファイルスコープ (グローバルまたは名前空間スコープ) で変数または関数を宣言する場合、 **`static`** キーワードは、変数または関数に内部リンケージがあることを指定します。 変数を宣言すると、変数は静的存続期間が設定され、コンパイラによって 0 に初期化されます (別の値を指定していない場合)。

1. 関数で変数を宣言する場合、キーワードは、 **`static`** 変数がその関数の呼び出し間で状態を保持することを指定します。

1. クラス宣言でデータメンバーを宣言する場合、キーワードは、 **`static`** メンバーの1つのコピーがクラスのすべてのインスタンスで共有されることを指定します。 静的データ メンバーはファイル スコープで定義する必要があります。 として宣言する整数データメンバーは、 **`const static`** 初期化子を持つことができます。

1. クラス宣言でメンバー関数を宣言する場合、キーワードは、その **`static`** 関数がクラスのすべてのインスタンスによって共有されることを指定します。 静的メンバー関数は、暗黙的なポインターがないため、インスタンスメンバーにアクセスできません **`this`** 。 インスタンス メンバーにアクセスするには、インスタンスのポインターまたは参照であるパラメーターを受け取る関数を宣言します。

1. 共用体のメンバーを static として宣言することはできません。 ただし、グローバルに宣言された匿名共用体は、明示的に宣言する必要があり **`static`** ます。

この例では、 **`static`** 関数内で宣言された変数が、その関数の呼び出し間で状態を保持する方法を示します。

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

この例では、クラスでのの使用方法を示し **`static`** ます。

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

この例では、メンバー関数で宣言されたローカル変数を示し **`static`** ます。 変数は、 **`static`** プログラム全体で使用できます。型のすべてのインスタンスは、変数の同じコピーを共有し **`static`** ます。

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

C++ 11 以降では、 **`static`** ローカル変数の初期化はスレッドセーフであることが保証されています。 この機能は、*マジックスタティック*と呼ばれることもあります。 ただし、マルチスレッド アプリケーションでは、後続の割り当てはすべて同期する必要があります。 スレッドセーフな静的初期化機能は、 [`/Zc:threadSafeInit-`](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) CRT への依存関係を回避するために、フラグを使用して無効にすることができます。

## <a name="extern"></a><a name="extern"></a> `extern`

として宣言 **`extern`** されたオブジェクトと変数は、別の翻訳単位または外側のスコープに外部リンケージがあるとして定義されているオブジェクトを宣言します。 詳細については、「」 [`extern`](extern-cpp.md) および「[翻訳単位とリンケージ](program-and-linkage-cpp.md)」を参照してください。

## <a name="thread_local-c11"></a><a name="thread_local"></a>`thread_local`(C++ 11)

指定子を使用して宣言された変数は、その変数が作成された **`thread_local`** スレッドでのみアクセスできます。 変数は、スレッドが作成されるときに作成され、スレッドが破棄されるときに破棄されます。 各スレッドには、それ自体の変数のコピーがあります。 Windows で **`thread_local`** は、は Microsoft 固有の属性と機能的には同等です [`__declspec( thread )`](../cpp/thread.md) 。

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

指定子について注意すべき点は **`thread_local`** 次のとおりです。

- Dll 内の動的に初期化されたスレッドローカル変数は、すべての呼び出し元スレッドで正しく初期化されない場合があります。 詳細については、「[`thread`](thread.md)」を参照してください。

- **`thread_local`** 指定子は、またはと組み合わせることができ **`static`** **`extern`** ます。

- は、 **`thread_local`** データの宣言と定義にのみ適用できます。 **`thread_local`** 関数の宣言または定義では使用できません。

- **`thread_local`** 静的ストレージ存続期間を持つデータ項目に対してのみ指定できます。 これには、グローバルデータオブジェクト ( **`static`** と **`extern`** の両方)、ローカルの静的オブジェクト、およびクラスの静的データメンバーが含まれます。 宣言されたローカル変数 **`thread_local`** は、他のストレージクラスが指定されていない場合は暗黙的に静的になります。つまり、ブロックスコープで **`thread_local`** はと同じに **`thread_local static`** なります。

- 宣言 **`thread_local`** と定義が同じファイルと個別のファイルのどちらで発生するかにかかわらず、スレッドローカルオブジェクトの宣言と定義の両方にを指定する必要があります。

Windows で **`thread_local`** は、 [`__declspec(thread)`](../cpp/thread.md) * は *`*__declspec(thread)`* 型定義に適用でき、C コードでは有効であることを除いて、機能的にはと同じです。 可能な限り、は C++ 標準の一部であるため、を使用し **`thread_local`** て移植性が高くなります。

## <a name="register"></a><a name="register"></a>取引

**Visual Studio 2017 バージョン15.3 以降**(で使用可能 [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`register`** キーワードはサポートされているストレージクラスではなくなりました。 キーワードは、将来使用するために標準で予約されています。

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>例: 自動初期化と静的初期化

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

この例では、オブジェクト、、、およびがいつどのように初期化され、いつ破棄されるかを示し `I1` `I2` `I3` ます。

プログラムに関して注意すべき点がいくつかあります。

- 最初に、制御フローが `I1` と `I2` を定義しているブロックを終了すると、これらは自動的に破棄されます。

- 次に、C++ では、ブロックの先頭でオブジェクトや変数を宣言する必要はありません。 さらに、これらのオブジェクトは、制御フローが定義に到達した場合にのみ初期化されます  ( `I2` と `I3` は、このような定義の例です)。出力は、初期化された時点で正確に示されます。

- 最後に、`I3` などの静的ローカル変数は、プログラム実行中は値が保持されますが、プログラムが終了すると破棄されます。

## <a name="see-also"></a>関連項目

[宣言と定義](../cpp/declarations-and-definitions-cpp.md)
