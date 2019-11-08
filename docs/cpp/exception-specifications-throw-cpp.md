---
title: 例外の仕様 (スロー、noexcept) (C++)
ms.date: 01/18/2018
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
ms.openlocfilehash: a3d4c0446cd8dde83febb1b4269811b5dec3c477
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222110"
---
# <a name="exception-specifications-throw-noexcept-c"></a>例外の仕様 (スロー、noexcept) (C++)

例外の仕様は、関数で伝えることができる例外の種類についてのプログラマの意図を示す C++ 言語機能です。 関数は可能性がありますかを使用して、例外によって終了可能性がありますを指定できます、*例外仕様*します。 コンパイラは、関数の呼び出しを最適化するためにこの情報を使用することができ、予期しない例外の場合、プログラムを終了する関数をエスケープします。

C++ 17 の前に、例外の指定の 2 種類がありました。 *Noexcept 仕様*c++ 11 で新しく追加されました。 これは、関数をエスケープできる潜在的な例外のセットが空かどうかを指定します。 *動的例外指定*、または`throw(optional_type_list)`仕様が c++ 11 で非推奨し、以外の c++ 17 では削除`throw()`のエイリアスである`noexcept(true)`します。 この例外の指定は、関数からスローできる例外に関する概要情報を提供するよう設計されましたが、実際に問題がある検出されました。 ある程度役に立つことが 1 つの動的例外指定が、無条件`throw()`仕様。 たとえば、関数宣言します。

```cpp
void MyFunction(int i) throw();
```
このコードでは、コンパイル時に関数が例外をスローしません。 ただし、 **/std:c++14**モードにする可能性が未定義の動作が、関数は例外をスローする場合。 使用して勧めそのため、 [noexcept](../cpp/noexcept-cpp.md)上ではなく演算子。

```cpp
void MyFunction(int i) noexcept;
```
次の表は、MicrosoftC++例外の仕様の実装。

|例外の指定|説明|
|-----------------------------|-------------|
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|関数は例外をスローしません。 [/Std:c + + 14](../build/reference/std-specify-language-standard-version.md)モード (既定)、`noexcept`と`noexcept(true)`は同等です。 宣言されている関数から例外をスローするときに`noexcept`または`noexcept(true)`、 [std::terminate](../standard-library/exception-functions.md#terminate)が呼び出されます。 として宣言されている関数から例外をスローするときに`throw()`で **/std:c + + + 14**モードでは、結果は未定義の動作です。 特定の関数は呼び出されません。 これは、コンパイラを呼び出すを必要とする、標準の c++ 14 からの逸脱[std::unexpected](../standard-library/exception-functions.md#unexpected)します。  <br/> **Visual Studio 2017 バージョン 15.5 以降**: **/Std:c + + 17**モード、 `noexcept`、 `noexcept(true)`、および`throw()`はすべて同等です。 **/Std:c + + 17**モード、`throw()`の別名です`noexcept(true)`します。 **/Std:c + + + 17**モードで、これらの仕様のいずれかで宣言された関数から例外がスローされたときに[std::terminate](../standard-library/exception-functions.md#terminate)が呼び出される標準の c++ 17 で必要とします。|
|`noexcept(false)`<br/>`throw(...)`<br/>なしの仕様|関数は、任意の型の例外をスローできます。|
|`throw(type)`| (**C++ 14 以降**)、関数型の例外をスローする`type`します。 コンパイラは、構文を受け入れますが、として解釈`noexcept(false)`します。 **/std:c++17**モード、コンパイラは警告 C5040 を発行します。|

例外処理をアプリケーションで使用する場合があります関数関数の外側のスコープを終了する前に、スローされた例外のハンドルがマークされている呼び出し履歴で`noexcept`、 `noexcept(true)`、または`throw()`します。 例外をスローする 1 つと、例外を処理する 1 つとして指定の間で任意の関数が呼び出された場合`noexcept`、 `noexcept(true)` (または`throw()`で **/std:c++17**モード)、プログラムが終了したときに、noexcept 関数には、例外が伝達されます。

関数の例外動作は、次の要因によって異なります。

- [言語標準のコンパイル モード](../build/reference/std-specify-language-standard-version.md)設定されます。
- C または C++ で関数をコンパイルするかどうか。

- これは、 [/EH](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを使用します。

- 例外の指定を明示的に使用するかどうか。

明示的な例外の指定は C 関数では使用できません。 C 関数が下の例外をスローしていないと見なされます **/EHsc**、構造化例外をスローする可能性が、 **/EHs**、 **/EHa**、または **/EHac**します。

次の表は、C++ 関数はさまざまなコンパイラ例外の処理オプションの下でスローすることは可能性がある可能性があるかどうかをまとめたものです。

|関数|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|例外を指定していない C++ 関数|はい|はい|はい|[はい]|
|C++ 関数`noexcept`、 `noexcept(true)`、または`throw()`例外の指定|いいえ|×|[はい]|[はい]|
|C++ 関数`noexcept(false)`、 `throw(...)`、または`throw(type)`例外の指定|はい|はい|はい|[はい]|

## <a name="example"></a>例

```cpp
// exception_specification.cpp
// compile with: /EHs
#include <stdio.h>

void handler() {
   printf_s("in handler\n");
}

void f1(void) throw(int) {
   printf_s("About to throw 1\n");
   if (1)
      throw 1;
}

void f5(void) throw() {
   try {
      f1();
   }
   catch(...) {
      handler();
    }
}

// invalid, doesn't handle the int exception thrown from f1()
// void f3(void) throw() {
//   f1();
// }

void __declspec(nothrow) f2(void) {
   try {
      f1();
   }
   catch(int) {
      handler();
    }
}

// only valid if compiled without /EHc
// /EHc means assume extern "C" functions don't throw exceptions
extern "C" void f4(void);
void f4(void) {
   f1();
}

int main() {
   f2();

   try {
      f4();
   }
   catch(...) {
      printf_s("Caught exception from f4\n");
   }
   f5();
}
```

```Output
About to throw 1
in handler
About to throw 1
Caught exception from f4
About to throw 1
in handler
```

## <a name="see-also"></a>関連項目

[try、throw、catch ステートメント (C++)](../cpp/try-throw-and-catch-statements-cpp.md)<br/>
[C++ 例外処理](../cpp/cpp-exception-handling.md)