---
title: 例外フィルターの記述
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: aaf0dc77207399d7c6be86127d7decf03895ced5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245987"
---
# <a name="writing-an-exception-filter"></a>例外フィルターの記述

例外は、例外ハンドラーのレベルにジャンプするか、実行を続けるかのいずれかにより、処理できます。 Instead of using the exception handler code to handle the exception and falling through, you can use *filter* to clean up the problem and then, by returning -1, resume normal flow without clearing the stack.

> [!NOTE]
>  一部の例外は、続行できない場合があります。 If *filter* evaluates to -1 for such an exception, the system raises a new exception. When you call [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception), you determine whether the exception will continue.

For example, the following code uses a function call in the *filter* expression: this function handles the problem and then returns -1 to resume normal flow of control:

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

It is a good idea to use a function call in the *filter* expression whenever *filter* needs to do anything complex. 式を評価すると、関数 (この場合、`Eval_Exception`) が実行されます。

Note the use of [GetExceptionCode](/windows/win32/Debug/getexceptioncode) to determine the exception. この関数は、フィルター自体の内部で呼び出す必要があります。 `Eval_Exception` cannot call `GetExceptionCode`, but it must have the exception code passed to it.

このハンドラーは、例外が整数または浮動小数点数のオーバーフローでなければ、他のハンドラーに制御を渡します。 オーバーフローがあった場合、ハンドラーは関数 (`ResetVars` は一例で、API 関数ではありません) を呼び出して、いくつかのグローバル関数をリセットします。 *Statement-block-2*, which in this example is empty, can never be executed because `Eval_Exception` never returns EXCEPTION_EXECUTE_HANDLER (1).

関数呼び出しの使用は、複雑なフィルター式を処理するための優れた汎用的手法です。 その他の便利な 2 つの C 言語機能を次に示します。

- 条件演算子

- コンマ演算子

条件演算子を使用すると、特定のリターン コードをチェックしてから 2 つの異なる値のいずれかを返すことができるため、この演算子は多くの場合に役立ちます。 For example, the filter in the following code recognizes the exception only if the exception is STATUS_INTEGER_OVERFLOW:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

次のコードでは同じ結果が生成されるため、ここでは条件演算子が主として明確さを高めるために使用されています。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

The conditional operator is more useful in situations where you might want the filter to evaluate to -1, EXCEPTION_CONTINUE_EXECUTION.

コンマ演算子を使用すると、1 つの式内で複数の個別演算を実行できます。 複数のステートメントを実行してから最後の式の値を返す場合とほぼ同じ効果が得られます。 たとえば、次のコードでは、変数に例外コードを保存してから、そのコードをテストしています。

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>関連項目

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)