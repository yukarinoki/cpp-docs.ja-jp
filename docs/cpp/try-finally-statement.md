---
title: try-finally ステートメント
description: __Try および __finally の構造化例外処理ステートメントへの Microsoft C++ リファレンス。
ms.date: 08/25/2020
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: edabbbe35c86f0305e31f36584c4dfe01f2f88cd
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898640"
---
# <a name="try-finally-statement"></a>`try-finally` ステートメント

`try-finally`ステートメントは、C および C++ 言語の構造化例外処理をサポートする、 **Microsoft 固有**の拡張機能です。

## <a name="syntax"></a>構文

次の構文では、ステートメントについて説明し `try-finally` ます。

```cpp
    // . . .
    __try {
        // guarded code
    }
    __finally {
        // termination code
    }
    // . . .
```

## <a name="grammar"></a>文法

> *`try-finally-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

`try-finally`ステートメントは、C および C++ 言語に対する Microsoft の拡張機能であり、コードのブロックの実行が中断された場合に、対象アプリケーションがクリーンアップコードの実行を保証できるようにします。 クリーンアップは、メモリを解放する、ファイルを閉じる、ファイル ハンドルを解放するなどのタスクで構成されます。 `try-finally` ステートメントは、ルーチンからの不完全な戻りが発生する可能性のあるエラーを複数の場所でチェックするルーチンに特に便利です。

関連情報とコードサンプルについては、「 [ `try-except` ステートメント](../cpp/try-except-statement.md)」を参照してください。 構造化例外処理全般の詳細については、「 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)」を参照してください。 C++/CLI を使用したマネージアプリケーションでの例外処理の詳細については、「」の「[例外処理 `/clr` ](../extensions/exception-handling-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
> 構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、特に C++ 用にデザインされたものではありません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 C++ プログラムでは、c++ 例外処理機構 ([ `try` 、 `catch` 、および `throw` ](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント) を使用することをお勧めします。

句の後の複合ステートメント **`__try`** は、保護されたセクションです。 **`__finally`** 句の後の複合ステートメントは、終了ハンドラーです。 ハンドラーは、保護されたセクションが終了したときに実行される一連のアクションを指定します。これは、保護されたセクションが例外によって終了するか (異常終了)、標準のフォールスルー (通常は終了) によって終了します。

制御は、 **`__try`** 単純な順次実行 (フォールスルー) によってステートメントに到達します。 コントロールがに入ると、 **`__try`** 関連付けられているハンドラーがアクティブになります。 制御のフローが try ブロックの終わりに到達すると、次のように実行は処理されます。

1. 終了ハンドラーが呼び出されます。

1. 終了ハンドラーが完了すると、 **`__finally`** ステートメントの後から実行が続けられます。 ただし、保護されたセクションは終了します (たとえば、保護された本文やステートメントを使用して **`goto`** **`return`** )。制御フローが保護されたセクションから移動 *する前に* 、終了ハンドラーが実行されます。

   ステートメントが、 **`__finally`** 適切な例外ハンドラーの検索をブロックしていません。

ブロックで例外が発生した場合 **`__try`** 、オペレーティングシステムは例外のハンドラーを見つける必要があります。見つからない場合、プログラムは失敗します。 ハンドラーが見つかった場合は、すべてのブロックとすべての **`__finally`** ブロックが実行され、ハンドラーで実行が再開されます。

たとえば、次の図に示すように、一連の関数呼び出しで、関数 A を関数 D にリンクするとします。 各関数には、1 つの終了ハンドラーがあります。 関数 D で例外が発生し、A で処理されると、スタックがアンワインドされるときに、終了ハンドラーは D、C、B の順に呼び出されます。

![終了&#45;ハンドラー実行の順序](../cpp/media/vc38cx1.gif "終了&#45;ハンドラー実行の順序") <br/>
終了順序 - ハンドラーの実行

> [!NOTE]
> Try-finally の動作は、C# などのの使用をサポートする他の言語とは異なり **`finally`** ます。  1つのには **`__try`** 、との両方を含めることはできません **`__finally`** **`__except`** 。  両方を一緒に使用する場合は、外側の try-except ステートメントで内側の try-finally ステートメントを囲む必要があります。  各ブロックがいつ実行されるかを指定する規則も異なります。

以前のバージョンとの互換性のため、、 **`_try`** **`_finally`** 、および **`_leave`** は **`__try`** 、 **`__finally`** **`__leave`** コンパイラオプション ([ [ `/Za` 言語拡張機能の無効化])](../build/reference/za-ze-disable-language-extensions.md)が指定されていない限り、、、およびのシノニムです。

## <a name="the-__leave-keyword"></a>__leave キーワード

キーワードは、 **`__leave`** ステートメントの保護されたセクション内でのみ有効で `try-finally` あり、その結果、保護されたセクションの末尾に移動します。 実行は、終了ハンドラーの最初のステートメントに移って続行されます。

ステートメントは、保護され **`goto`** たセクションからジャンプすることもできますが、スタックアンワインドを呼び出すため、パフォーマンスが低下します。 **`__leave`** ステートメントは、スタックアンワインドが発生しないため、より効率的です。

## <a name="abnormal-termination"></a>異常終了

`try-finally` [Longjmp](../c-runtime-library/reference/longjmp.md)ランタイム関数を使用してステートメントを終了すると、異常終了と見なされます。 ステートメントにジャンプするのは有効 **`__try`** ではありませんが、1つから除外することはできます。 **`__finally`** 出発点 (ブロックの通常の終了 **`__try`** ) と変換先 (例外を処理するブロック) の間でアクティブなすべてのステートメントを **`__except`** 実行する必要があります。 これは、 *ローカルアンワインド*と呼ばれます。

ブロックから **`__try`** のジャンプなど、何らかの理由でブロックが途中で終了した場合、システムは **`__finally`** スタックのアンワインドのプロセスの一部として、関連付けられているブロックを実行します。 このような場合、 [`AbnormalTermination`](/windows/win32/Debug/abnormaltermination) 関数は、 **`true`** ブロック内から呼び出された場合はを返します **`__finally`** 。それ以外の場合はを返し **`false`** ます。

ステートメントの実行中にプロセスが強制終了した場合、終了ハンドラーは呼び出されません `try-finally` 。

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[終了ハンドラーの構文](/windows/win32/Debug/termination-handler-syntax)
