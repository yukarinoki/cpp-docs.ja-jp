---
title: 例外フィルターの記述
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: 05d3aa79d1293001e80a77b3171b7a4607cd81c7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369483"
---
# <a name="writing-an-exception-filter"></a>例外フィルターの記述

例外は、例外ハンドラーのレベルにジャンプするか、実行を続けるかのいずれかにより、処理できます。 例外ハンドラー コードを使用して例外を処理して通過させる代わりに、*フィルター*を使用して問題をクリーンアップし、-1 を返してスタックをクリアせずに通常のフローを再開できます。

> [!NOTE]
> 一部の例外は、続行できない場合があります。 このような例外に対して*フィルター*が -1 と評価された場合、システムは新しい例外を発生させます。 を呼び出すときに[、](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception)例外が続行するかどうかを決定します。

たとえば、次のコードは *、フィルター*式で関数呼び出しを使用します: この関数は、問題を処理し、次に 、制御の通常のフローを再開する -1 を返します。

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

*フィルター*が複雑な操作を行う必要がある場合は、*フィルター*式で関数呼び出しを使用することをお勧めします。 式を評価すると、関数 (この場合、`Eval_Exception`) が実行されます。

例外を決定するために[GetExceptionCode](/windows/win32/Debug/getexceptioncode)を使用することに注意してください。 この関数は、フィルター自体の内部で呼び出す必要があります。 `Eval_Exception`呼び`GetExceptionCode`出すことはできませんが、例外コードが渡されている必要があります。

このハンドラーは、例外が整数または浮動小数点数のオーバーフローでなければ、他のハンドラーに制御を渡します。 オーバーフローがあった場合、ハンドラーは関数 (`ResetVars` は一例で、API 関数ではありません) を呼び出して、いくつかのグローバル関数をリセットします。 この例では、ステートメント*ブロック-2*は空ですが、EXCEPTION_EXECUTE_HANDLER (1)`Eval_Exception`を返すことはないため、実行できません。

関数呼び出しの使用は、複雑なフィルター式を処理するための優れた汎用的手法です。 その他の便利な 2 つの C 言語機能を次に示します。

- 条件演算子

- コンマ演算子

条件演算子を使用すると、特定のリターン コードをチェックしてから 2 つの異なる値のいずれかを返すことができるため、この演算子は多くの場合に役立ちます。 たとえば、次のコードのフィルターは、例外がSTATUS_INTEGER_OVERFLOW場合にのみ例外を認識します。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

次のコードでは同じ結果が生成されるため、ここでは条件演算子が主として明確さを高めるために使用されています。

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

条件演算子は、フィルターを -1、EXCEPTION_CONTINUE_EXECUTIONに評価する場合に便利です。

コンマ演算子を使用すると、1 つの式内で複数の個別演算を実行できます。 複数のステートメントを実行してから最後の式の値を返す場合とほぼ同じ効果が得られます。 たとえば、次のコードでは、変数に例外コードを保存してから、そのコードをテストしています。

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>関連項目

[例外ハンドラーの作成](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
