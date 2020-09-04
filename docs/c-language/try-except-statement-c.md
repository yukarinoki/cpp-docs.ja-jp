---
title: try-except ステートメント (C)
description: Microsoft C/C++ では、try-except ステートメント言語拡張を使用した構造化例外処理 (SEH) が実装されています。
ms.date: 08/24/2020
helpviewer_keywords:
- try-except keyword [C]
- structured exception handling, try-except
- try-catch keyword [C]
- __try keyword [C]
- __except keyword [C]
- __except keyword [C], in try-except
- try-catch keyword [C], try-except keyword [C]
ms.assetid: f76db9d1-fc78-417f-b71f-18e545fc01c3
ms.openlocfilehash: e327150431fef3384f2b98940939444b2e6d96ea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898728"
---
# <a name="try-except-statement-c"></a>try-except ステートメント (C)

**Microsoft 固有の仕様**

`try-except` ステートメントは、C 言語に対する Microsoft の拡張機能であり、正常に実行を終了するイベントが発生したときに、アプリケーションがプログラムの制御を取得できるようにします。 このようなイベントは例外と呼ばれ、例外を処理する機構は構造化例外処理と呼ばれます。

例外は、ハードウェアベースまたはソフトウェアベースのいずれかです。 アプリケーションがハードウェア例外またはソフトウェア例外から完全に回復できない場合でも、構造化例外処理ではエラー情報をログに記録し、表示することができます。 これは、問題を診断するために、アプリケーションの内部状態を把握するのに役立ちます。 特に、再現するのが難しい断続的な問題に対して役立ちます。

## <a name="syntax"></a>構文

> *`try-except-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__except (`**  *`expression`*  **`)`** *`compound-statement`*

**`__try`** 句の後の複合ステートメントは、"*保護されたセクション*" です。 **`__except`** 句の後の複合ステートメントは、"*例外ハンドラー*" です。 ハンドラーによって、保護されたセクションの実行中に例外が発生した場合に実行する一連のアクションを指定します。 次のように実行されます。

1. 保護されたセクションが実行されます。

1. 保護されたセクションの実行中に例外が発生しなかった場合、実行は **`__except`** 句の後のステートメントから続行されます。

1. 保護されたセクションの実行中、または保護されたセクションで呼び出された任意のルーチンで例外が発生した場合、 **`__except`** 式が評価されます。 返される値によって、例外の処理方法が決まります。 指定可能な 3 つの値は次のとおりです。

   - `EXCEPTION_CONTINUE_SEARCH`:例外は認識されません。 最初に `try-except` ステートメントを含むハンドラーを検索してから、次に優先順位が最も高いハンドラーについてスタックを検索し続けます。

   - `EXCEPTION_CONTINUE_EXECUTION`:例外は認識されますが、無視されます。 例外が発生した位置から実行を継続します。

   - `EXCEPTION_EXECUTE_HANDLER` 例外は認識されます。 **`__except`** 複合ステートメントの実行によって例外ハンドラーに制御を移動した後、例外が発生した時点から実行を続行します。

**`__except`** 式は C の式として評価されるため、1 つの値、条件式の演算子、またはコンマ演算子のいずれかに制限されます。 より広範な処理が必要な場合、前に挙げた 3 つの値の 1 つを返すルーチンを式で呼び出すことができます。

> [!NOTE]
> 構造化例外処理は、C および C++ のソース ファイルに機能します。 ただし、特に C++ 用にデザインされたものではありません。 移植可能な C++ プログラムでは、構造化例外処理ではなく、C++ 例外処理を使用する必要があります。 また、C++ 例外処理メカニズムは、任意の型の例外を処理できるという点で、より柔軟です。 詳細については、「*C++ 言語リファレンス*」の[例外処理](../cpp/exception-handling-in-visual-cpp.md)に関する記事をご覧ください。

アプリケーションの各ルーチンには、それぞれ独自の例外ハンドラーがある場合があります。 **`__except`** 式は、 **`__try`** 本体のスコープ内で実行されます。 そこで宣言された任意のローカル変数にアクセスできます。

**`__leave`** キーワードは、`try-except` ステートメント ブロック内で有効です。 **`__leave`** の効果は、`try-except` ブロックの末尾に移動することです。 実行は、例外ハンドラーの終了後に再開します。 **`goto`** ステートメントを使用しても同じ結果が得られますが、 **`goto`** ステートメントではスタックがアンワインドされます。 **`__leave`** ステートメントは、スタック アンワインドを伴わないため、より効率的です。

`longjmp` ランタイム関数を使用して `try-except` ステートメントを終了すると、異常終了と見なされます。 **`__try`** ステートメントにジャンプして入ることはできませんが、このステートメントからジャンプして出ることはできます。 例外ハンドラーは、`try-except` ステートメントの実行中にプロセスが中止された場合は呼び出されません。

## <a name="example"></a>例

例外ハンドラーと終了ハンドラーの例を次に示します。 終了ハンドラーの詳細については、「[`try-finally` ステートメント (C)](../c-language/try-finally-statement-c.md)」をご覧ください。

```C
.
.
.
puts("hello");
__try {
   puts("in try");
   __try {
      puts("in try");
      RAISE_AN_EXCEPTION();
   } __finally {
      puts("in finally");
   }
} __except( puts("in filter"), EXCEPTION_EXECUTE_HANDLER ) {
   puts("in except");
}
puts("world");
```

例の出力を次に示します。右側にコメントが追加されています。

```Output
hello
in try              /* fall into try                        */
in try              /* fall into nested try                 */
in filter           /* execute filter; returns 1 so accept  */
in finally          /* unwind nested finally                */
in except           /* transfer control to selected handler */
world               /* flow out of handler                  */
```

**Microsoft 固有の仕様の終了**

## <a name="see-also"></a>関連項目

[`try-except` ステートメント (C++)](../cpp/try-except-statement.md)
