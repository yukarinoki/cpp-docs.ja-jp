---
title: new および delete 演算子
ms.date: 05/07/2019
f1_keywords:
- delete_cpp
- new
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 8dd5e6a555872c443e32e9ea464ea49d4ae18f99
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222366"
---
# <a name="new-and-delete-operators"></a>new および delete 演算子

C++ は、[new](../cpp/new-operator-cpp.md) と[削除](../cpp/delete-operator-cpp.md) 演算子を使用したオブジェクトの動的な割り当てと解放をサポートしています。 これらの演算子は、フリー ストアと呼ばれるプールからオブジェクトにメモリを割り当てます。 **新しい**演算子は、特殊な関数を呼び出す[演算子 new](../cpp/new-operator-cpp.md)、および**削除**演算子は、特殊な関数を呼び出す[演算子 delete](../cpp/delete-operator-cpp.md).

C++標準ライブラリの **new** 関数は、C++標準で指定された動作をサポートします。これは、メモリの割り当てに失敗した場合に、std::bad_alloc 例外をスローします。 でも、スローしないバージョンの **new** が必要な場合、プログラムを nothrownew.obj とリンクしてください。ただし、nothrownew.obj とリンクすると、C++ 標準ライブラリでは既定の **operator new** は機能しなくなります。

C ランタイム ライブラリと C++ 標準ライブラリを構成するライブラリ ファイルの一覧は、次を参照してください。 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)します。

##  <a id="new_operator"> </a> new 演算子

プログラム内で次のようなステートメントが検出されると、関数の呼び出し **new 演算子** に変換されます。

```cpp
char *pch = new char[BUFFER_SIZE];
```

要求がゼロ バイトのストレージの場合、**new 演算子** は別のオブジェクトへのポインターを返します (つまり、**new 演算子** の繰り返し呼び出しには異なるポインターが返されます)。割り当て要求に十分なメモリがない場合、**new 演算子** は std::bad_alloc 例外をスローするか、非スロー**new 演算子**のサポートにリンクしている場合は、 **nullptr** を返します。

メモリを解放して、割り当てを再試行しようとするルーチンを記述することができます。参照してください[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)詳細についてはします。 復旧方法の詳細については、このトピックの処理が不足しているメモリのセクションを参照してください。

**new 演算子**関数の 2 つのスコープは次の表で説明します。

### <a name="scope-for-operator-new-functions"></a>operator new 関数のスコープ

|演算子|スコープ|
|--------------|-----------|
|**: new 演算子**|Global|
|*class-name* **::operator new**|クラス|

**new 演算子** の最初の引数は`size_t 型`(\<stddef.h >で定義されている型) でなければならず、戻り値の型は常に、**void** <strong>\*</strong> です。

グローバル **new 演算子** 関数は、**new** を使用した組み込み型のオブジェクト、ユーザー定義演算子の**new 演算子**　を含まないクラス型のオブジェクト、および任意の型の配列を割る当てるときに呼び出されます。**new** 演算子を使用して、**new 演算子** が定義されているクラス型のオブジェクトを割り当てる場合、そのクラスの **new 演算子** が呼び出されます。

クラスに定義された **new 演算子** は、そのクラス型のオブジェクトのグローバルな **new 演算子**関数を非表示にする静的メンバー関数です(そのため、仮想にはできません)。**new** を使用して、メモリを割り当て、指定した値に設定にする場合を考えてみます。

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

**new** のかっこで指定された引数は、`chInit` 引数として、`Blanks::operator new` に渡されます。 ただし、グローバル **new 演算子**関数は非表示になっているため、次のコードでエラーが生成されます。

```cpp
Blanks *SomeBlanks = new Blanks;
```

コンパイラは、クラス宣言でメンバーの配列の **new** と **delete** 演算子をサポートします。 例:

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

##  <a id="delete_operator"> </a> delete 演算子

**new** 演算子を使用して動的に割り当てられているメモリは、**delete** 演算子を使用して解放することができます。 delete 演算子は **delete 演算子** 関数を呼び出します。これにより、使用可能なプールにメモリが解放されます。**delete** 演算子を使用することで、クラスのデストラクター (存在する場合) も呼び出されます。

グローバルとクラス スコープがある**delete 演算子**関数。 1 つだけ**delete 演算子**関数は、特定のクラスに対して定義できます。、定義されている場合、非表示に、グローバル**delete 演算子**関数。 グローバル**delete 演算子**関数が常に任意の型の配列に対して呼び出されます。

グローバル**delete 演算子**関数。 2 つの形式は、グローバルの存在**delete 演算子**およびクラス メンバー **delete 演算子**関数。

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

上記の 2 つの形式の 1 つだけは、特定のクラスに対して使用できます。 最初の形式では、型の 1 つの引数を受け取ります`void *`、割り当てを解除するオブジェクトへのポインターが含まれています。 2 番目の形式: サイズ割り当て解除、割り当てを解除するメモリ ブロックへのポインター 1 つ目は、2 番目の割り当てを解除するバイト数は、2 つの引数します。 両方のフォームの戻り値の型は**void** (**delete 演算子**値を返すことはできません)。

2 番目の形式の目的は、多くの場合自体割り当て近接して格納し、キャッシュを無効可能性があります。 速度、削除するオブジェクトの適切なサイズのカテゴリの検索をする2 番目の形式が役立つ場合に、 **delete 演算子**基底クラスから関数を使用して、派生クラスのオブジェクトを削除します。

**delete 演算子** 関数は静的です。そのため、仮想化することはできません。 **delete 演算子** 関数は、[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md) の説明に従ってアクセスの制御に従います。

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

上記のコードを使用して "メモリ リーク" の検出に使うことができます。メモリ リークとは、フリー ストアに割り当てられ、解放されていないメモリを指します。 この検出は、グローバルな **new** と **delete** 演算子が再定義され、メモリの数の割り当てと解除をカウントします。

コンパイラは、クラス宣言でメンバー配列の **new** と **delete** 演算子をサポートします。 例:

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
