---
title: C++ で構造化例外を処理します。
ms.date: 08/14/2018
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 2c4f1a8c3729e2b4d49a0152425e57717f7e9997
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154413"
---
# <a name="handle-structured-exceptions-in-c"></a>C++ で構造化例外を処理します。

C の主な違いに構造化例外処理 (SEH) と C++ 例外処理は、C++ 例外の種類のモデルの取引を処理、C の中に構造化例外処理モデルで処理される 1 つの型の例外具体的には、**符号なし int**します。つまり、C 例外は符号なし整数値で識別されますが、C++ 例外はデータ型で識別されます。 C 構造化例外が発生すると、可能な各ハンドラーは、C 例外コンテキストを調べ、例外を受け入れる、他のハンドラーに渡すこと、またはそれを無視するかどうかを決定するフィルターを実行します。 C++ でスローされる例外は、どのような型でもかまいません。

2 つ目の違いは、C 構造化例外処理モデルが呼んでいる*非同期*にセカンダリを通常の制御フローに例外が発生するため、します。 C++ 例外処理メカニズムが完全に*同期*例外がスローされたときにのみ発生することを意味します。

使用すると、 [/EHs または/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプション、なしの C++ 例外の処理の構造化例外ハンドラー。 これらの例外の処理でのみ **__catch**例外ハンドラーを構造化または **_ _finally**終了ハンドラーを構成します。 詳しくは、次を参照してください。[構造化例外処理 (c/c++)](structured-exception-handling-c-cpp.md)します。

下、 [/EHa](../build/reference/eh-exception-handling-model.md)コンパイラ オプションは、C++ プログラムでは、C 例外が発生する場合に処理できる、関連付けられているフィルターを使用して構造化例外ハンドラーまたは C++ **catch** 方ハンドラー例外コンテキスト動的に近い。 たとえば、次の C++ プログラムは内部、C++ で C 例外を発生させます。**お試しください**コンテキスト。

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>例 - Catch、C++ で C 例外のキャッチ ブロック

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

## <a name="c-exception-wrapper-classes"></a>C 例外のラッパー クラス

上記のような簡単な例で、省略記号によってのみ、C の例外をキャッチできます ( **.** )**キャッチ**ハンドラー。 ハンドラーに伝達される例外の種類または特性に関する情報はありません。 このメソッドは、場合によっては可能性があるそれぞれの C 例外は、特定のクラスに関連付けできるように、2 つの例外処理モデル間の変換を定義します。 これを行うために、特定のクラスの種類を C 例外に起因すると見なすために利用したり派生させたりできる、C 例外の "wrapper" クラスを定義できます。 これにより、各 C 例外が処理されるとは別に、特定の c++**キャッチ**ではなく、単一のハンドラーでそれらのすべてのハンドラー。

ラッパー クラスには、例外の値を決定して、C 例外モデルが提供する拡張例外コンテキスト情報にアクセスするメンバー関数で構成されるインターフェイスが含まれることがあります。 既定のコンス トラクターとを受け入れるコンス トラクターを定義することも、**符号なし int** (C 例外の基になる表現を提供) への引数、およびビットごとのコピー コンス トラクター。 次に、C 例外のラッパー クラスの実装を示します。

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

このクラスを使用するには、によって内部例外処理機構を C 例外がスローされるたびに呼び出されるカスタム C 例外変換関数をインストールします。 変換関数内では、任意の型指定された例外をスローします (おそらく、`SE_Exception`型、またはクラス型から派生した`SE_Exception`) を適切な一致する C++ でキャッチできる**キャッチ**ハンドラー。 変換関数は、単純に制御を返すことができます。これは、例外を処理しなかったことを示します。 変換関数自体が C の例外が発生した場合[終了](../c-runtime-library/reference/terminate-crt.md)が呼び出されます。

カスタム変換関数を指定するには、呼び出し、 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md)関数の 1 つの引数として、変換関数の名前に置き換えます。 作成した変換関数を持つスタックの関数呼び出しごとに 1 回呼び出されます。**お試しください**ブロックします。 既定の変換関数はありません。呼び出して 1 つを指定しない場合 **_set_se_translator**、C 例外は、省略記号によってのみキャッチできます**キャッチ**ハンドラー。

## <a name="example---use-a-custom-translation-function"></a>例 - カスタム変換関数を使用

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

[C (構造化) と C++ 例外の混合](../cpp/mixing-c-structured-and-cpp-exceptions.md)
