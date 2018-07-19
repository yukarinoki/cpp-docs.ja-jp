---
title: 例外の仕様 (スロー、noexcept) (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ab09d5aadb489208b2e7591c2bf0f60ab836da4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417601"
---
# <a name="exception-specifications-throw-noexcept-c"></a>例外の仕様 (スロー、noexcept) (C++)

例外の指定は、関数によって伝達されることができます、例外の種類に関するプログラマの意図を示す C++ 言語の機能です。 関数がいるかを使用して、例外によって終了可能性がありますを指定することができます、*例外指定*です。 コンパイラは、この情報を使用して、関数への呼び出しを最適化するために、関数をエスケープする場合、予期しない例外は、プログラムを終了する. 

C++ 17 の前に、2 種類の例外の指定がありました。 *Noexcept 仕様*が c++ 11 の新機能です。 これは、関数をエスケープする可能性がある例外のセットが空かどうかを指定します。 *動的例外指定*、または`throw(optional_type_list)`仕様が c++ 11 で廃止されました、以外の c++ 17、削除された`throw()`のエイリアスである`noexcept(true)`です。 この例外の指定された関数の場合からどのような例外をスローできる概要情報を提供するように設計されていますが、実際には、見つかった問題があること。 ある程度役に立つことが 1 つの動的な例外の仕様は、無条件`throw()`仕様です。 たとえば、関数宣言します。

```cpp
void MyFunction(int i) throw();
```
このコードでは、コンパイル時に関数が例外をスローしません。 ただし、 **/std:c + + 14**場合は、関数は例外をスローする可能性がモード未定義の動作です。 そのためことをお勧めを使用して、 [noexcept](../cpp/noexcept-cpp.md)上ではなく演算子。

```cpp
void MyFunction(int i) noexcept;
```
次の表は、例外の指定の Microsoft Visual C の実装をまとめたものです。

|例外の指定|説明|
|-----------------------------|-------------|
|`noexcept`<br>`noexcept(true)`<br>`throw()`|関数は例外をスローしません。 [/Std:c + + 14](../build/reference/std-specify-language-standard-version.md)モード (既定値)、`noexcept`と`noexcept(true)`は同等です。 宣言された関数から例外がスローされたときに`noexcept`または`noexcept(true)`、 [std::terminate](../standard-library/exception-functions.md#terminate)が呼び出されます。 として宣言された関数から例外がスローされたときに`throw()`で **/std:c + + 14**モードでは、結果は未定義の動作です。 特定の関数は呼び出されません。 これは、コンパイラを呼び出すを必要とする、標準の c++ 14 の相違[std::unexpected](../standard-library/exception-functions.md#unexpected)です。  <br> **Visual Studio 2017 15.5 およびそれ以降のバージョン**: で **/std:c + + 17**モード、 `noexcept`、 `noexcept(true)`、および`throw()`はすべて同等です。 **/Std:c + + 17**モード、`throw()`のエイリアス`noexcept(true)`です。 **/Std:c + + 17**モードで、これらの仕様のいずれかで宣言された関数から例外がスローされる[std::terminate](../standard-library/exception-functions.md#terminate)が呼び出される、c++ 17 規格による要求どおりです。|
|`noexcept(false)`<br/>`throw(...)`<br/>ない仕様|関数は、任意の型の例外をスローできます。|
|`throw(type)`| (**C++ 14 およびそれ以前**)、関数、型の例外がスロー`type`です。 コンパイラは、構文を受け入れますとして解釈`noexcept(false)`です。 **/Std:c + + 17**モード、コンパイラは警告 C5040 を発行します。|

場合は、アプリケーションでは、例外処理を使用する必要があります関数、関数の外側のスコープを終了する前に、スローされた例外のハンドルがマークされている呼び出し履歴で`noexcept`、 `noexcept(true)`、または`throw()`です。 例外をスローする 1 つと、例外を処理する 1 つとして指定の間ですべての関数が呼び出された場合`noexcept`、 `noexcept(true)` (または`throw()`で **/std:c + + 17**モード)、プログラムが終了したときに、noexcept 関数には、例外が伝達されます。

関数の例外の動作は、次の要因によって異なります。

- [言語標準コンパイル モード](../build/reference/std-specify-language-standard-version.md)が設定されています。
- C または C++ で関数をコンパイルするかどうか。

- [/EH](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを使用します。

- 例外の指定を明示的に使用するかどうか。

明示的な例外の指定は C 関数では使用できません。 C の関数をスローしないはずの下の例外 **/EHsc**、下にある構造化例外をスローする可能性がありますと **/EHs**、 **/EHa**、または **/EHac**です。

次の表では、C++ 関数はさまざまなコンパイラ例外の処理オプションでスローすることは可能性がある可能性があるかどうかをまとめたものです。

|関数|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|例外を指定していない C++ 関数|[はい]|はい|はい|[はい]|
|C++ の関数を`noexcept`、 `noexcept(true)`、または`throw()`例外の指定|×|Ｘ|はい|[はい]|
|C++ の関数を`noexcept(false)`、 `throw(...)`、または`throw(type)`例外の指定|[はい]|はい|はい|[はい]|

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

 [try、throw、および catch ステートメント (C++)](../cpp/try-throw-and-catch-statements-cpp.md) [C++ 例外処理](../cpp/cpp-exception-handling.md)