---
title: 例外フィルターの記述
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: 2bc159247604877fb22ff6084e1fda36946561a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209378"
---
# <a name="writing-an-exception-filter"></a>例外フィルターの記述

例外は、例外ハンドラーのレベルにジャンプするか、実行を続けるかのいずれかにより、処理できます。 例外ハンドラーのコードを使用して、フォール スルーと、例外を処理するために、代わりに使用することができます*フィルター*問題をクリーンアップし、その後、-1 を返すことによってスタックを消去しないで標準フローを再開します。

> [!NOTE]
>  一部の例外は、続行できない場合があります。 場合*フィルター*評価システムにこのような例外の場合は-1、新しい例外を発生させます。 呼び出すと[RaiseException](https://msdn.microsoft.com/library/windows/desktop/ms680552)、例外を続行するかどうかを判断します。

次のコードが関数呼び出しを使用するなど、*フィルター*式: この関数は、問題を処理し、通常の制御フローを再開する場合は-1 を返します。

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

内の関数呼び出しを使用することをお勧め、*フィルター*式たびに*フィルター*複雑な何もする必要があります。 式を評価すると、関数 (この場合、`Eval_Exception`) が実行されます。

使用に注意してください[GetExceptionCode](/windows/desktop/Debug/getexceptioncode)例外を判断します。 この関数は、フィルター自体の内部で呼び出す必要があります。 `Eval_Exception` 呼び出すことはできません`GetExceptionCode`、例外コードを渡す必要がありますが、します。

このハンドラーは、例外が整数または浮動小数点数のオーバーフローでなければ、他のハンドラーに制御を渡します。 オーバーフローがあった場合、ハンドラーは関数 (`ResetVars` は一例で、API 関数ではありません) を呼び出して、いくつかのグローバル関数をリセットします。 *ステートメント ブロック 2*、ために、この例では、空を実行しないことができます`Eval_Exception`EXCEPTION_EXECUTE_HANDLER (1) を返すことはありません。

関数呼び出しの使用は、複雑なフィルター式を処理するための優れた汎用的手法です。 その他の便利な 2 つの C 言語機能を次に示します。

- 条件演算子

- コンマ演算子

条件演算子を使用すると、特定のリターン コードをチェックしてから 2 つの異なる値のいずれかを返すことができるため、この演算子は多くの場合に役立ちます。 たとえば、次のコードでのフィルターは、例外が STATUS_INTEGER_OVERFLOW である場合にのみ例外を認識します。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

次のコードでは同じ結果が生成されるため、ここでは条件演算子が主として明確さを高めるために使用されています。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

条件演算子は、-1、EXCEPTION_CONTINUE_EXECUTION を評価するフィルターが必要がある状況で役立ちます。

コンマ演算子を使用すると、1 つの式内で複数の個別演算を実行できます。 複数のステートメントを実行してから最後の式の値を返す場合とほぼ同じ効果が得られます。 たとえば、次のコードでは、変数に例外コードを保存してから、そのコードをテストしています。

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)