---
title: new および delete 演算子
ms.date: 11/19/2019
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: fd170c1500e2d80879fdd89f7d825930189ae942
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367886"
---
# <a name="new-and-delete-operators"></a>new および delete 演算子

C++ では[、new](new-operator-cpp.md)演算子と[delete](delete-operator-cpp.md)演算子を使用してオブジェクトの動的割り当てと割り当て解除がサポートされます。 これらの演算子は、フリー ストアと呼ばれるプールからオブジェクトのメモリを割り当てます。 **new**演算子は特殊関数[演算子](new-operator-cpp.md)new を呼び出し **、delete**演算子は特殊関数[演算子 delete](delete-operator-cpp.md)を呼び出します。

C++ 標準ライブラリの**新しい**関数は、C++ 標準で指定された動作 bad_allocをサポートしています。 スローしないバージョンの**新しい**を引き続き使用する場合は、プログラムを nothrownew.obj にリンクします。ただし、nothrownew.obj でリンクすると、C++ 標準ライブラリの**既定の演算子**が機能しなくなります。

C ランタイム ライブラリと C++ 標準ライブラリを構成するライブラリ ファイルの一覧については、「 [CRT ライブラリ機能](../c-runtime-library/crt-library-features.md)」を参照してください。

## <a name="the-new-operator"></a><a id="new_operator"> </a>新しい演算子

プログラムで次のようなステートメントが検出されると、関数**演算子**new の呼び出しに変換されます。

```cpp
char *pch = new char[BUFFER_SIZE];
```

要求がゼロ・バイトのストレージの場合 **、operator new**は、別個のオブジェクトへのポインターを戻します (つまり、**オペレーター new**への反復呼び出しは異なるポインターを戻します)。 割り当て要求に対して十分なメモリがない場合、`std::bad_alloc`演算子**new**は例外をスローします。 **nullptr** **operator new**

メモリを解放して割り当てを再試行するルーチンを記述できます。詳細については[、_set_new_handler](../c-runtime-library/reference/set-new-handler.md)を参照してください。 回復スキームの詳細については、このトピックの「メモリ不足の処理」を参照してください。

**演算子の新しい**関数の 2 つのスコープを次の表に示します。

### <a name="scope-for-operator-new-functions"></a>演算子の新しい関数のスコープ

|演算子|Scope|
|--------------|-----------|
|**::オペレータ新しい**|グローバル|
|*クラス名* **::演算子新しい**|クラス|

**new 演算子**の最初の引数は型`size_t`(stddef.h>で\<定義されている型) でなければならず、戻り値の型は常に void**です**<strong>\*</strong>。

new**演算子の新しい**関数は、**new**組み込み型のオブジェクト、ユーザー定義演算子の**新しい**関数を含まないクラス型のオブジェクト、および任意の型の配列を割り当てるときに呼び出されます。 **new**演算子が定義されているクラス型のオブジェクトを割り当てるときに **、new**演算子を使用すると、そのクラスの**演算子 new**が呼び出されます。

クラスに対して定義される**演算子の新しい**関数は、そのクラス型のオブジェクトのグローバル**演算子の新しい**関数を隠す静的メンバー関数 (したがって、仮想にすることはできません) です。 new**を使用**してメモリを割り当て、指定した値に設定する場合を考えてみましょう。

```cpp
#include <malloc.h>
#include <memory.h>

class Blanks
{
public:
    Blanks(){}
    void *operator new( size_t stAllocateBlock, char chInit );
};
void *Blanks::operator new( size_t stAllocateBlock, char chInit )
{
    void *pvTemp = malloc( stAllocateBlock );
    if( pvTemp != 0 )
        memset( pvTemp, chInit, stAllocateBlock );
    return pvTemp;
}
// For discrete objects of type Blanks, the global operator new function
// is hidden. Therefore, the following code allocates an object of type
// Blanks and initializes it to 0xa5
int main()
{
   Blanks *a5 = new(0xa5) Blanks;
   return a5 != 0;
}
```

**new**にかっこで囲んで指定された引数は`Blanks::operator new`、引数`chInit`として渡されます。 ただし、グローバル**演算子の新しい**関数は非表示になり、次のようなコードでエラーが発生します。

```cpp
Blanks *SomeBlanks = new Blanks;
```

コンパイラは、クラス宣言でメンバー配列**new**演算子と**delete**演算子をサポートしています。 次に例を示します。

```cpp
class MyClass
{
public:
   void * operator new[] (size_t)
   {
      return 0;
   }
   void   operator delete[] (void*)
   {
   }
};

int main()
{
   MyClass *pMyClass = new MyClass[5];
   delete [] pMyClass;
}
```

### <a name="handling-insufficient-memory"></a>メモリ不足の処理

次に示すように、メモリ割り当てが失敗した場合のテストを行うことができます。

```cpp
#include <iostream>
using namespace std;
#define BIG_NUMBER 100000000
int main() {
   int *pI = new int[BIG_NUMBER];
   if( pI == 0x0 ) {
      cout << "Insufficient memory" << endl;
      return -1;
   }
}
```

失敗したメモリ割り当て要求を処理する別の方法があります。 このようなエラーを処理するカスタム回復ルーチンを作成し、_set_new_handler[ランタイム関数](../c-runtime-library/reference/set-new-handler.md)を呼び出して関数を登録します。

## <a name="the-delete-operator"></a><a id="delete_operator"> </a>削除演算子

**new**演算子を使用して動的に割り当てられたメモリは **、delete**演算子を使用して解放できます。 delete 演算子は、使用可能なプールにメモリを解放する**演算子削除**関数を呼び出します。 **delete**演算子を使用すると、クラスデストラクター (存在する場合) も呼び出されます。

グローバルおよびクラススコープの**演算子削除**関数があります。 指定したクラスに対して定義できる**演算子削除**関数は 1 つだけです。定義されている場合は、グローバル**演算子削除**関数が非表示になります。 グローバル**演算子 delete**関数は、任意の型の配列に対して常に呼び出されます。

グローバル**演算子削除**関数。 グローバル**演算子削除**関数とクラスメンバー**演算子**削除関数には、次の 2 つの形式があります。

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

指定されたクラスに対して、前の 2 つのフォームのうち 1 つだけを指定できます。 最初の形式は、割り当てを`void *`解除するオブジェクトへのポインターを含む type の引数を 1 つ取ります。 2 番目の形式 (サイズ解放) は 2 つの引数を受け取り、最初の引数は割り当て解除するメモリ ブロックへのポインタであり、2 番目は割り当て解除するバイト数です。 両方の形式の戻り値の型は**void**です (**演算子 delete**は値を返すことができません)。

2 番目の形式の目的は、削除するオブジェクトの正しいサイズ カテゴリの検索を高速化することです。 2 番目の形式は、基底クラスからの**演算子削除**関数を使用して派生クラスのオブジェクトを削除する場合に便利です。

**演算子削除**関数は静的です。したがって、仮想にすることはできません。 **オペレーター削除**機能は、メンバーアクセス制御 の説明に従ってアクセス[制御に](member-access-control-cpp.md)従います。

次の例は、メモリの割り当てと割り当て解除をログに記録するように設計された、ユーザー定義**の演算子 new**関数および**operator delete**関数を示しています。

```cpp
#include <iostream>
using namespace std;

int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?
int cBlocksAllocated = 0;  // Count of blocks allocated.

// User-defined operator new.
void *operator new( size_t stAllocateBlock ) {
   static int fInOpNew = 0;   // Guard flag.

   if ( fLogMemory && !fInOpNew ) {
      fInOpNew = 1;
      clog << "Memory block " << ++cBlocksAllocated
          << " allocated for " << stAllocateBlock
          << " bytes\n";
      fInOpNew = 0;
   }
   return malloc( stAllocateBlock );
}

// User-defined operator delete.
void operator delete( void *pvMem ) {
   static int fInOpDelete = 0;   // Guard flag.
   if ( fLogMemory && !fInOpDelete ) {
      fInOpDelete = 1;
      clog << "Memory block " << cBlocksAllocated--
          << " deallocated\n";
      fInOpDelete = 0;
   }

   free( pvMem );
}

int main( int argc, char *argv[] ) {
   fLogMemory = 1;   // Turn logging on
   if( argc > 1 )
      for( int i = 0; i < atoi( argv[1] ); ++i ) {
         char *pMem = new char[10];
         delete[] pMem;
      }
   fLogMemory = 0;  // Turn logging off.
   return cBlocksAllocated;
}
```

上記のコードを "メモリ リーク" の検出に使うことができます。メモリ リークとは、フリー ストアに割り当てられ、解放されていないメモリを指します。 この検出を実行するために、グローバル**な新規**および**削除**演算子が、メモリの割り当てと割り当て解除をカウントするように再定義されます。

コンパイラは、クラス宣言でメンバー配列**new**演算子と**delete**演算子をサポートしています。 次に例を示します。

```cpp
// spec1_the_operator_delete_function2.cpp
// compile with: /c
class X  {
public:
   void * operator new[] (size_t) {
      return 0;
   }
   void operator delete[] (void*) {}
};

void f() {
   X *pX = new X[5];
   delete [] pX;
}
```
