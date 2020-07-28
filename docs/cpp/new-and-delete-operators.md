---
title: new および delete 演算子
description: C++ 言語の new および delete 演算子を使用すると、割り当てを制御できます。
ms.date: 07/07/2020
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.openlocfilehash: e609d1fdbd4f945ab8709c554d1396100027c4c1
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127858"
---
# <a name="new-and-delete-operators"></a>`new` 演算子と `delete` 演算子

C++ では、および演算子を使用したオブジェクトの動的な割り当てと解放がサポートされてい [`new`](new-operator-cpp.md) [`delete`](delete-operator-cpp.md) ます。 これらの演算子は、フリー ストアと呼ばれるプールからオブジェクトのメモリを割り当てます。 **`new`** 演算子は特殊な関数を呼び出し、 [`operator new`](new-operator-cpp.md) **`delete`** 演算子は特殊な関数を呼び出し [`operator delete`](delete-operator-cpp.md) ます。

**`new`** C++ 標準ライブラリの関数は、c++ 標準で指定された動作をサポートします。これは、メモリ割り当てが失敗した場合に例外をスローし `std::bad_alloc` ます。 それでものスローされないバージョンが必要な場合は **`new`** 、プログラムをにリンク *`nothrownew.obj`* します。 ただし、とリンクすると *`nothrownew.obj`* 、C++ 標準ライブラリの既定値は **`operator new`** 機能しなくなります。

C ランタイムライブラリと C++ 標準ライブラリのライブラリファイルの一覧については、「 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。

## <a name="the-new-operator"></a><a id="new_operator"> </a> `new` 演算子

コンパイラは、次のようなステートメントを関数の呼び出しに変換し **`operator new`** ます。

```cpp
char *pch = new char[BUFFER_SIZE];
```

要求のサイズがゼロバイトのストレージである場合、は **`operator new`** 別のオブジェクトへのポインターを返します。 つまり、を繰り返し呼び出して、 **`operator new`** 異なるポインターを返します。 割り当て要求のメモリが不足している場合、は **`operator new`** 例外をスロー `std::bad_alloc` します。 または、 **`nullptr`** 非スローサポートにリンクしている場合は、を返し **`operator new`** ます。

メモリの解放を試み、割り当てを再試行するルーチンを記述できます。 詳細については、「[`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)」を参照してください。 復旧スキームの詳細については、「[メモリ不足の処理](#handling-insufficient-memory)」を参照してください。

次の表では、関数の2つのスコープに **`operator new`** ついて説明します。

### <a name="scope-for-operator-new-functions"></a>関数のスコープ `operator new`

| 演算子 | スコープ |
|--|--|
| **`::operator new`** | グローバル |
| *クラス名***`::operator new`** | クラス |

の最初の引数は **`operator new`** 、型であり、で定義されている必要があり、 `size_t` \<stddef.h> 戻り値の型は常に **`void*`** です。

グローバル **`operator new`** 関数は、 **`new`** 組み込み型のオブジェクト、ユーザー定義関数を含まないクラス型のオブジェクト、および任意の型の配列を割り当てるために演算子が使用されるときに呼び出され **`operator new`** ます。 **`new`** が定義されているクラス型のオブジェクトを割り当てるために演算子が使用されて **`operator new`** いる場合、そのクラスの **`operator new`** が呼び出されます。

**`operator new`** クラスに対して定義された関数は、 **`operator new`** そのクラス型のオブジェクトのグローバル関数を隠す静的メンバー関数です (仮想にすることはできません)。 を使用して **`new`** メモリを割り当て、指定された値に設定する場合を考えてみます。

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

にかっこで指定された引数は、 **`new`** `Blanks::operator new` 引数としてに渡され `chInit` ます。 ただし、グローバル **`operator new`** 関数は非表示になっているため、次のようなコードがエラーを生成します。

```cpp
Blanks *SomeBlanks = new Blanks;
```

コンパイラは、クラス宣言でメンバー配列と演算子をサポートしてい **`new`** **`delete`** ます。 次に例を示します。

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

次に示すように、失敗したメモリ割り当てのテストを行うことができます。

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

失敗したメモリ割り当て要求を処理する別の方法があります。 このようなエラーを処理するカスタム復旧ルーチンを記述し、実行時関数を呼び出して関数を登録し [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md) ます。

## <a name="the-delete-operator"></a><a id="delete_operator"> </a> `delete` 演算子

演算子を使用して動的に割り当てられたメモリは **`new`** 、演算子を使用して解放でき **`delete`** ます。 Delete 操作は、 **`operator delete`** 使用可能なプールにメモリを解放する関数を呼び出します。 また、 **`delete`** 演算子を使用すると、クラスデストラクター (存在する場合) が呼び出されます。

グローバルおよびクラススコープの関数があり **`operator delete`** ます。 特定の **`operator delete`** クラスに対して定義できる関数は1つだけです。定義されている場合は、グローバル関数が非表示になり **`operator delete`** ます。 グローバル **`operator delete`** 関数は、常に任意の型の配列に対して呼び出されます。

グローバル **`operator delete`** 関数。 グローバル **`operator delete`** 関数とクラスメンバー関数には、次の2つの形式があり **`operator delete`** ます。

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

指定されたクラスには、前の2つのフォームのうち1つだけが存在できます。 最初のフォームは、型の1つの引数を受け取ります。この引数には、 **`void *`** 割り当てを解除するオブジェクトへのポインターが含まれています。 2番目の形式の割り当て解除では、2つの引数を取ります。1つ目は、割り当てを解除するメモリブロックへのポインターで、2番目は割り当てを解除するバイト数です。 両方の形式の戻り値の型は、 **`void`** ( **`operator delete`** 値を返すことはできません) です。

2番目の形式の目的は、削除するオブジェクトの正しいサイズカテゴリの検索を高速化することです。 多くの場合、この情報は割り当て自体の近くに格納されず、キャッシュされない可能性があります。 2番目の形式は、 **`operator delete`** 派生クラスのオブジェクトを削除するために基底クラスの関数を使用する場合に便利です。

**`operator delete`** 関数は静的であるため、仮想にすることはできません。 **`operator delete`** 関数は、「[メンバー Access Control](member-access-control-cpp.md)」で説明されているように、アクセス制御に従います。

次の例は、 **`operator new`** **`operator delete`** メモリの割り当てと割り当て解除を記録するように設計されたユーザー定義関数と関数を示しています。

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

前のコードを使用して、"メモリリーク"、つまり、無料ストアに割り当てられているが解放されていないメモリを検出することができます。 リークを検出するために、グローバル **`new`** および **`delete`** 演算子はメモリの割り当てと解放をカウントするように再定義されています。

コンパイラは、クラス宣言でメンバー配列と演算子をサポートしてい **`new`** **`delete`** ます。 次に例を示します。

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
