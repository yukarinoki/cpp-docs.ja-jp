---
description: 構造化例外フィルターの記述方法については、こちらを参照してください。
title: 例外フィルターの記述
ms.date: 12/16/2020
helpviewer_keywords:
- exception handling [C++], filters
ms.openlocfilehash: 8b6706c7dfe0e96e26f77f1f3a452db638141803
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645060"
---
# <a name="writing-an-exception-filter"></a>例外フィルターの記述

例外は、例外ハンドラーのレベルにジャンプするか、実行を続けるかのいずれかにより、処理できます。 例外ハンドラーコードを使用して例外を処理し、処理を遅延させる代わりに、 *フィルター* 式を使用して問題をクリーンアップできます。 次に (-1) を返すことで、 `EXCEPTION_CONTINUE_EXECUTION` スタックをクリアせずに通常のフローを再開できます。

> [!NOTE]
> 一部の例外は、続行できない場合があります。 このような例外に対して *filter* が-1 と評価された場合、システムによって新しい例外が発生します。 を呼び出すと [`RaiseException`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) 、例外を続行するかどうかが決定されます。

たとえば、次のコードでは、 *フィルター* 式で関数呼び出しを使用しています。この関数は問題を処理し、-1 を返して通常の制御フローを再開します。

```cpp
// exceptions_Writing_an_Exception_Filter.cpp
#include <windows.h>
int main() {
   int Eval_Exception( int );

   __try {}

   __except ( Eval_Exception( GetExceptionCode( ))) {
      ;
   }

}
void ResetVars( int ) {}
int Eval_Exception ( int n_except ) {
   if ( n_except != STATUS_INTEGER_OVERFLOW &&
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions
   return EXCEPTION_CONTINUE_SEARCH;

   // Execute some code to clean up problem
   ResetVars( 0 );   // initializes data to 0
   return EXCEPTION_CONTINUE_EXECUTION;
}
```

フィルターで複雑な処理を行う必要がある場合 *は常に*、*フィルター* 式で関数呼び出しを使用することをお勧めします。 式を評価すると、関数 (この場合、`Eval_Exception`) が実行されます。

例外を特定するために、を使用することに注意して [`GetExceptionCode`](/windows/win32/Debug/getexceptioncode) ください。 この関数は、ステートメントのフィルター式の内部で呼び出す必要があり **`__except`** ます。 `Eval_Exception` を呼び出すことはできません `GetExceptionCode` が、例外コードを渡す必要があります。

このハンドラーは、例外が整数または浮動小数点数のオーバーフローでなければ、他のハンドラーに制御を渡します。 オーバーフローがあった場合、ハンドラーは関数 (`ResetVars` は一例で、API 関数ではありません) を呼び出して、いくつかのグローバル関数をリセットします。 **`__except`** ステートメントブロック (この例では空) は、 `Eval_Exception` (1) を返さないため、実行できません `EXCEPTION_EXECUTE_HANDLER` 。

関数呼び出しの使用は、複雑なフィルター式を処理するための優れた汎用的手法です。 その他の便利な 2 つの C 言語機能を次に示します。

- 条件演算子

- コンマ演算子

ここでは、多くの場合、条件演算子が役立ちます。 これを使用すると、特定のリターンコードを確認し、2つの異なる値のいずれかを返すことができます。 たとえば、次のコードのフィルターは、例外がの場合にのみ例外を認識し `STATUS_INTEGER_OVERFLOW` ます。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

次のコードでは同じ結果が生成されるため、ここでは条件演算子が主として明確さを高めるために使用されています。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

条件演算子は、フィルターを-1 に評価する必要がある場合に便利です `EXCEPTION_CONTINUE_EXECUTION` 。

コンマ演算子を使用すると、複数の式を順番に実行できます。 次に、最後の式の値を返します。 たとえば、次のコードでは、変数に例外コードを保存してから、そのコードをテストしています。

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
