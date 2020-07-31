---
title: C++ での構造化例外の処理
description: C++ 例外処理モデルを使用して構造化例外を処理する方法。
ms.date: 09/19/2019
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 0f92bbe64db028ec6a7fd6ae2cc217c707d3e2c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221589"
---
# <a name="handle-structured-exceptions-in-c"></a>C++ での構造化例外の処理

C 構造化例外処理 (SEH) と C++ 例外処理の主な違いは、C++ 例外処理モデルが型を扱うのに対し、C 構造化例外処理モデルは1つの型の例外を処理することです。具体的には、 **`unsigned int`** です。 つまり、C 例外は符号なし整数値で識別されますが、C++ 例外はデータ型で識別されます。 構造化例外が C で発生した場合、考えられる各ハンドラーは、C 例外コンテキストを検査し、例外を受け入れるか、他のハンドラーに渡すか、または無視するかを決定するフィルターを実行します。 C++ でスローされる例外は、どのような型でもかまいません。

2つ目の違いは、C 構造化例外処理モデルを*非同期*と呼びます。これは、例外が通常の制御フローに対して実行されるためです。 C++ 例外処理機構は完全に*同期*されています。つまり、例外がスローされた場合にのみ発生します。

[/Ehs または/ehsc](../build/reference/eh-exception-handling-model.md)コンパイラオプションを使用する場合、C++ 例外ハンドラーは構造化例外を処理しません。 これらの例外は、 **`__except`** 構造化例外ハンドラーまたは構造化終了ハンドラーによってのみ処理され **`__finally`** ます。 詳細については、「[構造化例外処理 (C/c + +)](structured-exception-handling-c-cpp.md)」を参照してください。

[/Eha](../build/reference/eh-exception-handling-model.md)コンパイラオプションでは、C++ プログラムで c 例外が発生した場合、その例外は、関連付けられたフィルターまたは c++ ハンドラーによって **`catch`** 、例外コンテキストに動的に近い方の構造化例外ハンドラーによって処理されます。 たとえば、次のサンプル C++ プログラムでは、C++ コンテキスト内で C 例外が発生し **`try`** ます。

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>例-C++ catch ブロックで C 例外をキャッチする

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

## <a name="c-exception-wrapper-classes"></a>C 例外ラッパークラス

上記のような単純な例では、C 例外は省略記号 (**...**) **`catch`** によってのみキャッチされます。ヘッダー. ハンドラーに伝達される例外の種類または特性に関する情報はありません。 このメソッドは動作しますが、場合によっては、2つの例外処理モデル間の変換を定義して、各 C 例外が特定のクラスに関連付けられるようにすることが必要になる場合があります。 変換するには、C 例外の "ラッパー" クラスを定義します。このクラスは、特定のクラス型を C 例外に属性を設定するために使用または派生させることができます。 これにより、各 C 例外は、 **`catch`** 1 つのハンドラーではなく、特定の C++ ハンドラーによって個別に処理できます。

ラッパー クラスには、例外の値を決定して、C 例外モデルが提供する拡張例外コンテキスト情報にアクセスするメンバー関数で構成されるインターフェイスが含まれることがあります。 また、既定のコンストラクターと引数を受け取るコンストラクター **`unsigned int`** (基になる C 例外の表現を提供するため)、およびビットごとのコピーコンストラクターを定義することもできます。 C 例外ラッパークラスの実装例を次に示します。

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

このクラスを使用するには、C 例外がスローされるたびに内部例外処理機構によって呼び出されるカスタム C 例外変換関数をインストールします。 変換関数内では、 `SE_Exception` `SE_Exception` 適切な一致する C++ ハンドラーによってキャッチされる、型指定された例外 (場合によっては型、またはから派生したクラス型) をスローでき **`catch`** ます。 代わりに、変換関数はを返すことができます。これは、例外が処理されなかったことを示します。 変換関数自体で C 例外が発生した場合、 [terminate](../c-runtime-library/reference/terminate-crt.md)が呼び出されます。

カスタム変換関数を指定するには、変換関数の名前を1つの引数として[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)関数を呼び出します。 記述する変換関数は、ブロックを持つスタックの関数呼び出しごとに1回呼び出され **`try`** ます。 既定の変換関数はありません。**_set_se_translator**を呼び出すことによって指定しない場合、C 例外は省略記号ハンドラーによってのみキャッチされ **`catch`** ます。

## <a name="example---use-a-custom-translation-function"></a>例-カスタム変換関数を使用する

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
