---
title: new および delete 演算子
ms.date: 11/04/2016
f1_keywords:
- delete_cpp
- new
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 1ac6282ecbf45f22e7dd66b94f8bccdbc4e505ce
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345896"
---
# <a name="new-and-delete-operators"></a>new および delete 演算子

C++ を使用してオブジェクトの動的な割り当てと解放をサポートしています、[新しい](../cpp/new-operator-cpp.md)と[削除](../cpp/delete-operator-cpp.md)演算子。 これらの演算子は、フリー ストアと呼ばれるプールからオブジェクトのメモリを割り当てます。 **新しい**演算子は、特殊な関数を呼び出す[演算子 new](../cpp/new-operator-cpp.md)、および**削除**演算子は、特殊な関数を呼び出す[演算子 delete](../cpp/delete-operator-cpp.md).

**新しい**で機能、C++標準ライブラリで指定された動作をサポートしている、C++標準である、メモリの割り当てが失敗した場合は、std::bad_alloc 例外をスローします。 でも、スローしないバージョンの場合**新しい**プログラムを nothrownew.obj とリンクします。ただし、場合 nothrownew.obj とリンクする、既定の**演算子 new** C++ 標準ライブラリでは機能しなくします。

C ランタイム ライブラリと C++ 標準ライブラリを構成するライブラリ ファイルの一覧は、次を参照してください。 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)します。

##  <a id="new_operator"> </a> New 演算子

関数の呼び出しに変換プログラムでは、次のようなステートメントが発生したときに**演算子 new**:

```cpp
char *pch = new char[BUFFER_SIZE];
```

要求がゼロ バイトのストレージの場合**new 演算子**別のオブジェクトへのポインターを返します (つまりへの呼び出しを繰り返す**new 演算子**異なるポインターが返されます)。 メモリ不足のため、割り当て要求がある場合**演算子 new** 、std::bad_alloc 例外をスローするかを返します**nullptr**スローしないでリンクしている場合**演算子 new**をサポートします。

メモリを解放して、割り当てを再試行しようとするルーチンを記述することができます。参照してください[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)詳細についてはします。 復旧方法の詳細については、このトピックの処理が不足しているメモリのセクションを参照してください。

2 つのスコープの**演算子 new**関数は次の表で説明します。

### <a name="scope-for-operator-new-functions"></a>operator new 関数のスコープ

|演算子|スコープ|
|--------------|-----------|
|**: new 演算子**|Global|
|*class-name* **::operator new**|クラス|

最初の引数**演算子 new**型でなければなりません`size_t`(で定義された型\<stddef.h >)、戻り値の型は常に**void** <strong>\*</strong>.

グローバル**演算子 new**関数が呼び出されます、**新しい**を含まないクラス型のオブジェクトのユーザー定義演算子を使用して、組み込み型のオブジェクトの割り当てを**演算子 new**関数、および任意の型の配列。 ときに、**新しい**演算子を使用して、クラス型のオブジェクトを割り当てる場所、 **new 演算子**が定義されている場合、そのクラスの**new 演算子**が呼び出されます。

**演算子 new**クラスは、グローバル非表示にする (これは、そのため、仮想できません) 静的メンバー関数に対して定義された関数**演算子 new**そのクラス型のオブジェクトの関数。 場合を考えてみます場所**新しい**の割り当てし、メモリの指定した値を設定するために使用します。

```cpp
// spec1_the_operator_new_function1.cpp
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

かっこで指定された引数**新しい**に渡される`Blanks::operator new`として、`chInit`引数。 ただし、グローバル**new 演算子**など、エラーを生成するには、次のコードの原因と、関数は隠されます。

```cpp
Blanks *SomeBlanks = new Blanks;
```

Visual C 5.0 以前のバージョンをクラス型とすべての配列で (のあったかどうかに関係なく**クラス**型) を使用して割り当て、**新しい**演算子は常にグローバル使用**演算子 new**関数。

Visual C 5.0 以降では、コンパイラはメンバーの配列をサポート**新しい**と**削除**クラス宣言で演算子。 例えば:

```cpp
// spec1_the_operator_new_function2.cpp
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

失敗したメモリ割り当てのテストは、次のようなコードを使用して実行できます。

```cpp
// insufficient_memory_conditions.cpp
// compile with: /EHsc
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

失敗したメモリ割り当て要求を処理する別の方法はあります: このようなエラーは、処理するカスタム リカバリ ルーチンを作成し、呼び出すことによって、関数を登録、 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md)ランタイム関数。

##  <a id="delete_operator"> </a> Delete 演算子

使用して動的に割り当てられているメモリ、**新しい**演算子を使用して解放することができます、**削除**演算子。 Delete 演算子の呼び出し、 **delete 演算子**関数で、使用可能なプールにメモリを解放します。 使用して、**削除**演算子ともクラスのデストラクター (存在する場合) 呼び出されます。

グローバルとクラス スコープがある**delete 演算子**関数。 1 つだけ**delete 演算子**関数は、特定のクラスに対して定義できます。、定義されている場合、非表示に、グローバル**delete 演算子**関数。 グローバル**delete 演算子**関数が常に任意の型の配列に対して呼び出されます。

グローバル**delete 演算子**関数。 2 つの形式は、グローバルの存在**delete 演算子**およびクラス メンバー **delete 演算子**関数。

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

上記の 2 つの形式の 1 つだけは、特定のクラスに対して使用できます。 最初の形式では、型の 1 つの引数を受け取ります`void *`、割り当てを解除するオブジェクトへのポインターが含まれています。 2 番目の形式: サイズ割り当て解除、割り当てを解除するメモリ ブロックへのポインター 1 つ目は、2 番目の割り当てを解除するバイト数は、2 つの引数します。 両方のフォームの戻り値の型は**void** (**delete 演算子**値を返すことはできません)。

2 番目の形式の目的は、多くの場合自体割り当て近接して格納し、キャッシュを無効可能性があります。 速度、削除するオブジェクトの適切なサイズのカテゴリの検索をする2 番目の形式が役立つ場合に、 **delete 演算子**基底クラスから関数を使用して、派生クラスのオブジェクトを削除します。

**Delete 演算子**関数は静的; 仮想そのため、できません。 **Delete 演算子**」の説明に従って関数がアクセスの制御に従います[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)します。

次の例は、ユーザー定義**new 演算子**と**delete 演算子**関数がメモリの割り当てと解放を記録するように設計します。

```cpp
// spec1_the_operator_delete_function1.cpp
// compile with: /EHsc
// arguments: 3
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

上記のコードを "メモリ リーク" の検出に使うことができます。メモリ リークとは、フリー ストアに割り当てられ、解放されていないメモリを指します。 この検出は、グローバルなを実行する**新しい**と**削除**演算子がメモリの数の割り当てと解放を再定義します。

Visual C 5.0 以降では、コンパイラはメンバーの配列をサポート**新しい**と**削除**クラス宣言で演算子。 例えば:

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