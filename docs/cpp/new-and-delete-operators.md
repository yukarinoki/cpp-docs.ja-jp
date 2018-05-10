---
title: 新しい演算子と delete 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- delete_cpp
- new
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7f411d05491294421202ae6d8a1b7cbbb4e1d47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="new-and-delete-operators"></a>new および delete 演算子

C++ を使用してオブジェクトの動的割り当てと解放がサポートしている、[新しい](../cpp/new-operator-cpp.md)と[削除](../cpp/delete-operator-cpp.md)演算子。 これらの演算子は、フリー ストアと呼ばれるプールからオブジェクトのメモリを割り当てます。 `new`演算子は特殊な関数を呼び出す[new 演算子](../cpp/new-operator-cpp.md)、および`delete`演算子は特殊な関数を呼び出す[delete 演算子](../cpp/delete-operator-cpp.md)です。  
  
 `new` C++ 標準ライブラリ内の関数は、メモリ割り当てが失敗した場合は、std::bad_alloc 例外をスローする、C++ 標準で指定された動作をサポートしています。 かどうかか例外をスローしないバージョンの`new`プログラムを nothrownew.obj とリンクします。ただし、リンクする場合を nothrownew.obj と、既定値`operator new`C++ 標準ライブラリでは機能しなくなります。  
  
 C ランタイム ライブラリおよび C++ 標準ライブラリを構成するライブラリ ファイルの一覧は、次を参照してください。 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)します。  
  
##  <a id="new_operator"> </a> New 演算子  
 次のようなステートメントがプログラムで検出された場合は、関数 `operator new` の呼び出しに変換されます。  
  
```cpp  
char *pch = new char[BUFFER_SIZE];  
```  
  
要求がゼロ バイトのストレージの場合**new 演算子**個別のオブジェクトへのポインターを返します (つまりへの呼び出しを繰り返す**new 演算子**別のポインターを返す)。 不足しているメモリの割り当て要求がある場合**new 演算子**std::bad_alloc 例外をスローするかを返します**nullptr**例外をスローしないでリンクしている場合`operator new`をサポートします。  
  
メモリを解放して; 割り当てを再試行しようとするルーチンを記述することができます。参照してください[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)詳細についてはします。 復旧方法の詳細については、このトピックの処理が不足しているメモリのセクションを参照してください。  

  
`operator new` 関数の 2 つのスコープの説明を次の表に示します。  
  
### <a name="scope-for-operator-new-functions"></a>operator new 関数のスコープ  
  
|演算子|スコープ|  
|--------------|-----------|  
|**: 演算子の new**|Global|  
|*クラス名* **:: 演算子の new**|クラス|  
  
 1 番目の引数**new 演算子**型でなければなりません**size_t** (で定義された型\<stddef.h >)、戻り値の型は常に**void \*** .  
  
 グローバル**new 演算子**関数が呼び出されます、**新しい**演算子を使用して、組み込み型のオブジェクトを割り当てる、含まれていないクラス型のオブジェクトのユーザー定義**演算子の new**関数、および任意の型の配列。 ときに、**新しい**演算子を使用して、クラス型のオブジェクトを割り当てる場所、 **new 演算子**定義されると、そのクラスの**new 演算子**と呼びます。  
  
 **New 演算子**クラスは、グローバルの表示と非静的メンバー関数 (これは、そのため、仮想できません) に対して定義された関数**new 演算子**そのクラス型のオブジェクトに対して関数。 場合を考えます場所**新しい**を割り当てるし、メモリの指定した値を設定するために使用します。  
  
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
  
 かっこ内で指定された引数**新しい**に渡される`Blanks::operator new`として、`chInit`引数。 ただし、グローバル**new 演算子**エラーを生成するには、次のようなコードの原因と、関数は隠されます。  
  
```cpp  
Blanks *SomeBlanks = new Blanks;  
```  
  
 Visual C 5.0 およびそれ以前、クラス型とすべての配列 (のいたかどうかに関係なく**クラス**型) を使用して割り当て、**新しい**演算子は常にグローバル使用**演算子の new**関数。  
  
 Visual C 5.0 以降では、コンパイラはメンバーの配列をサポート**新しい**と**削除**クラス宣言内の演算子。 例えば:  
  
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
  
 失敗したメモリ割り当て要求を処理する別の方法がある: などの障害に対処するカスタム リカバリ ルーチンを記述し、呼び出すことによって、関数を登録、 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md)ランタイム関数。  
  
##  <a id="delete_operator"> </a> Delete 演算子  
 動的に割り当てられたメモリを使用して、**新しい**演算子を使用して解放することができます、**削除**演算子。 Delete 演算子の呼び出し、**演算子 delete**関数で、使用可能なプールにメモリを解放します。 使用して、**削除**演算子もが、クラスのデストラクター (1 つである) 場合に呼び出されます。  
  
 グローバルとクラス スコープがある**演算子 delete**関数。 1 つだけ**演算子 delete**関数は、特定のクラスに対して定義できます以外の場合は、定義されている場合がグローバルを隠す**演算子 delete**関数。 グローバル**演算子 delete**関数が常に任意の型の配列に対して呼び出されます。  
  
 グローバル**演算子 delete**関数。 2 つの形式は、グローバルの存在**演算子 delete**およびクラス メンバー**演算子 delete**関数。  
  
```cpp  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 上記の 2 つの形式の 1 つのみは、特定のクラスの存在することができます。 最初の形式で、1 つの引数型の**void \*** 、割り当てを解除するオブジェクトへのポインターが含まれています。 2 番目の形式: サイズ割り当て解除-最初の割り当てを解除するメモリ ブロックへのポインター、2 番目の割り当てを解除するバイト数の 2 つの引数を使用します。 両方のフォームの戻り値の型は`void`(**演算子 delete**値を返すことはできません)。  
  
 2 番目の形式の目的は、高速化、削除するオブジェクトの適切なサイズのカテゴリの検索は、ほとんどの場合、割り当て自体の近くに格納され、キャッシュを使用しないで可能性があります。2 番目の形式は特に便利だときに、**演算子 delete**基底クラスから関数を使用して、派生クラスのオブジェクトを削除します。  
  
 **演算子 delete**関数は静的です。 そのため、その仮想できません。 `operator delete` 」の説明に従って、関数は、アクセス制御を従う[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)です。  
  
 次の例は、ユーザー定義**new 演算子**と**delete 演算子**関数のメモリの割り当てと解放を記録するよう設計されています。  
  
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
  
 上記のコードを "メモリ リーク" の検出に使うことができます。メモリ リークとは、フリー ストアに割り当てられ、解放されていないメモリを指します。 グローバルに、この検出を実行する**新しい**と**削除**演算子がメモリのカウントの割り当てと解放を再定義します。  
  
 Visual C 5.0 以降では、コンパイラはメンバーの配列をサポート**新しい**と**削除**クラス宣言内の演算子。 例えば:  
  
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

