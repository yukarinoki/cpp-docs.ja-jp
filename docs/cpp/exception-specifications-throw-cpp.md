---
description: '詳細情報: 例外の指定 (throw、noexcept) (C++)'
title: 例外の指定 (throw、noexcept) (C++)
ms.date: 01/18/2018
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
ms.openlocfilehash: a6b3cb808caf464dc3dd19ea4d34e9d68f09d0d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164802"
---
# <a name="exception-specifications-throw-noexcept-c"></a>例外の指定 (throw、noexcept) (C++)

例外指定は、関数によって伝達される例外の種類についてプログラマが意図していることを示す C++ 言語機能です。 例外 *指定* を使用して、例外によって関数が終了するか、または終了しないかを指定できます。 コンパイラは、この情報を使用して関数の呼び出しを最適化し、予期しない例外によって関数がエスケープされた場合にプログラムを終了することができます。

C++ 17 より前では、2種類の例外指定がありました。 *Noexcept 仕様* は c++ 11 で新しく追加されました。 関数をエスケープできる可能性のある例外のセットが空であるかどうかを指定します。 *動的例外指定*( `throw(optional_type_list)` 仕様) は c++ 11 で非推奨とされ、c++ 17 では削除されました `throw()` 。ただし、の別名であるを除き `noexcept(true)` ます。 この例外指定は、関数からスローされる可能性がある例外に関する概要情報を提供するように設計されていますが、実際には、問題があることがわかりました。 やや有用であると証明された1つの動的例外指定は、無条件の仕様でした `throw()` 。 たとえば、関数宣言は次のようになります。

```cpp
void MyFunction(int i) throw();
```

このコードでは、コンパイル時に関数が例外をスローしません。 ただし、 **/std: c++ 14** モードでは、関数が例外をスローした場合に、未定義の動作が発生する可能性があります。 したがって、上記のいずれでもなく、 [noexcept](../cpp/noexcept-cpp.md) 演算子を使用することをお勧めします。

```cpp
void MyFunction(int i) noexcept;
```

次の表は、Microsoft C++ での例外指定の実装の概要を示しています。

|例外の指定|説明|
|-----------------------------|-------------|
|**`noexcept`**<br/>`noexcept(true)`<br/>`throw()`|関数は例外をスローしません。 [/Std: c++ 14](../build/reference/std-specify-language-standard-version.md)モード (既定) で **`noexcept`** は、と `noexcept(true)` は等価です。 またはとして宣言された関数から例外がスローされると **`noexcept`** `noexcept(true)` 、 [std:: terminate](../standard-library/exception-functions.md#terminate) が呼び出されます。 `throw()` **/Std: c++ 14** モードでとして宣言された関数から例外がスローされると、結果は未定義の動作になります。 特定の関数は呼び出されません。 これは C++ 14 標準の相違点であり、コンパイラが [std::](../standard-library/exception-functions.md#unexpected)を呼び出す必要がありました。  <br/> **Visual Studio 2017 バージョン15.5 以降**: **/std: c++ 17** モードでは、、、 **`noexcept`** `noexcept(true)` および `throw()` はすべて同等です。 **/Std: c++ 17** モードで `throw()` は、はのエイリアスです `noexcept(true)` 。 **/Std: c++ 17** モードでは、これらのいずれかの仕様で宣言された関数から例外がスローされると、c++ 17 標準によって必要に応じて [std:: terminate](../standard-library/exception-functions.md#terminate)が呼び出されます。|
|`noexcept(false)`<br/>`throw(...)`<br/>指定なし|関数は、任意の型の例外をスローできます。|
|`throw(type)`| (**C++ 14 以前**)関数は、型の例外をスローでき `type` ます。 コンパイラは構文を受け入れますが、として解釈し `noexcept(false)` ます。 **/Std: c++ 17** モードでは、コンパイラは警告 C5040 を発行します。|

アプリケーションで例外処理を使用する場合は **`noexcept`** 、、 `noexcept(true)` 、またはとマークされた関数の外側のスコープを終了する前にスローされた例外を処理する関数がコールスタックに存在する必要があり `throw()` ます。 例外をスローする関数と例外を処理する関数の間で呼び出された関数が **`noexcept`** 、 `noexcept(true)` (または `throw()` **/std: c++ 17** モード) として指定されている場合、noexcept 関数が例外を反映するとプログラムは終了します。

関数の例外動作は、次の要因によって異なります。

- [標準コンパイルモード](../build/reference/std-specify-language-standard-version.md)が設定されている言語。
- C または C++ で関数をコンパイルするかどうか。

- 使用する [/EH](../build/reference/eh-exception-handling-model.md) コンパイラオプション。

- 例外の指定を明示的に使用するかどうか。

明示的な例外の指定は C 関数では使用できません。 C 関数は、 **/ehsc** で例外をスローしないことを前提としており、 **/ehs**、 **/eha**、または **/EHac** の下で構造化例外をスローすることがあります。

次の表は、さまざまなコンパイラ例外処理オプションで C++ 関数がスローする可能性があるかどうかをまとめたものです。

|機能|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|例外を指定していない C++ 関数|はい|はい|はい|はい|
|**`noexcept`**、 `noexcept(true)` 、または `throw()` 例外指定を使用した C++ 関数|いいえ|いいえ|はい|はい|
|`noexcept(false)`、 `throw(...)` 、または `throw(type)` 例外指定を使用した C++ 関数|はい|はい|はい|はい|

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
[例外とエラー処理に関する最新の C++ のベストプラクティス](errors-and-exception-handling-modern-cpp.md)
