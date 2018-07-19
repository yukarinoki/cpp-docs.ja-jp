---
title: 例外処理の相違点 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dafb3c41bd490e7c123e1aefe9ccaa04a4e6b233
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943558"
---
# <a name="exception-handling-differences"></a>例外処理の相違点
構造化例外処理と C++ 例外処理の主な違いは、C++ 例外の種類のモデルの取引を処理、C の中に構造化例外処理モデルで処理される 1 つの型、具体的には、 **符号なし int**します。つまり、C 例外は符号なし整数値で識別されますが、C++ 例外はデータ型で識別されます。 例外が C で発生すると、可能な各ハンドラーは、C 例外コンテキストをチェックするフィルターを実行して、例外を受け入れるか、他のハンドラーに渡すか、または無視するかを決定します。 C++ でスローされる例外は、どのような型でもかまいません。  
  
 2 番目の相違点は、例外がコントロールの標準フローに従属的に発生すると C の構造化例外処理モデルが "非同期" と呼ばれることです。 C++ の例外処理機構は、完全な "同期処理" を提供します。つまり、例外は、スローされたときにのみ発生します。  
  
 C++ プログラムでは、C 例外が発生する場合に処理できる、関連付けられているフィルターを使用して構造化例外ハンドラーまたは C**キャッチ**ハンドラー、どちらが動的に近い例外コンテキスト。 たとえば、次の C++ プログラムは内部、C++ で C 例外を発生させます。**お試しください**コンテキスト。  
  
## <a name="example"></a>例  
  
```cpp 
// exceptions_Exception_Handling_Differences.cpp  
// compile with: /EHa  
#include <iostream>  
  
using namespace std;  
void SEHFunc( void );  
  
int main() {  
   try {  
      SEHFunc();  
   }  
   catch( ... ) {  
      cout << "Caught a C exception."<< endl;  
   }  
}  
  
void SEHFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
   }  
   __finally {  
      cout << "In finally." << endl;  
   }  
}  
```  
  
```Output  
In finally.  
Caught a C exception.  
```  
  
##  <a name="_core_c_exception_wrapper_class"></a> C 例外のラッパー クラス  
 上記のような簡単な例で、省略記号によってのみ、C の例外をキャッチできます (**.**)**キャッチ**ハンドラー。 ハンドラーに伝達される例外の種類または特性に関する情報はありません。 このメソッドは動作しますが、場合によっては、それぞれの C 例外が特定のクラスに関連付けられるように、2 つの例外処理モデル間の変換を定義する必要があります。 これを行うために、特定のクラスの種類を C 例外に起因すると見なすために利用したり派生させたりできる、C 例外の "wrapper" クラスを定義できます。 これにより、C++ で C の例外を処理できる**キャッチ**ハンドラーよりも個別に前の例です。  
  
 ラッパー クラスには、例外の値を決定して、C 例外モデルが提供する拡張例外コンテキスト情報にアクセスするメンバー関数で構成されるインターフェイスが含まれることがあります。 既定のコンス トラクターとを受け入れるコンス トラクターを定義することも、**符号なし int** (C 例外の基になる表現を提供) への引数、およびビットごとのコピー コンス トラクター。 次は、C 例外のラッパー クラスの実装の例です。  
  
```cpp 
// exceptions_Exception_Handling_Differences2.cpp  
// compile with: /c  
class SE_Exception {  
private:  
   SE_Exception() {}  
   SE_Exception( SE_Exception& ) {}  
   unsigned int nSE;  
public:  
   SE_Exception( unsigned int n ) : nSE( n ) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() {  
      return nSE;  
   }  
};  
  
```  
  
 このクラスを使用するには、C 例外がスローされるたびに内部例外処理メカニズムによって呼び出されるカスタム C 例外変換関数をインストールします。 変換関数内では、任意の型指定された例外をスローします (おそらく、`SE_Exception`型、またはクラス型から派生した`SE_Exception`) を適切な一致する C++ でキャッチできる**キャッチ**ハンドラー。 変換関数は、単純に制御を返すことができます。これは、例外を処理しなかったことを示します。 変換関数自体が C の例外が発生した場合[終了](../c-runtime-library/reference/terminate-crt.md)が呼び出されます。  
  
 カスタム変換関数を指定するには、呼び出し、 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md)関数の 1 つの引数として、変換関数の名前に置き換えます。 作成した変換関数を持つスタックの関数呼び出しごとに 1 回呼び出されます。**お試しください**ブロックします。 既定の変換関数はありません。呼び出して 1 つを指定しない場合`_set_se_translator`、C 例外は、省略記号によってのみキャッチできます**キャッチ**ハンドラー。  
  
## <a name="example"></a>例  
 たとえば、次のコードでは、カスタム変換関数がインストールされた後に、`SE_Exception` クラスでラップされた C 例外が発生します。  
  
```cpp 
// exceptions_Exception_Handling_Differences3.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <eh.h>  
#include <windows.h>  
  
class SE_Exception {  
private:  
   SE_Exception() {}  
   unsigned int nSE;  
  
public:  
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}  
   SE_Exception(unsigned int n) : nSE(n) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() { return nSE; }  
};  
  
void SEFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
    }  
    __finally {  
      printf_s( "In finally\n" );  
   }  
}  
  
void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {  
   printf_s( "In trans_func.\n" );  
   throw SE_Exception( u );  
}  
  
int main() {  
   _set_se_translator( trans_func );  
    try {  
      SEFunc();  
    }  
    catch( SE_Exception e ) {  
      printf_s( "Caught a __try exception with SE_Exception.\n" );  
      printf_s( "nSE = 0x%x\n", e.getSeNumber() );  
    }  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
nSE = 0xc0000094  
```  
  
## <a name="see-also"></a>関連項目  
 [C (構造化) と C++ の混合例外](../cpp/mixing-c-structured-and-cpp-exceptions.md)