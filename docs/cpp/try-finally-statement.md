---
title: try-finally ステートメント
ms.date: 11/19/2018
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
ms.openlocfilehash: c26b72f7c675a4130f38c515cf71ecc290328ccc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498603"
---
# <a name="try-finally-statement"></a>try-finally ステートメント

**Microsoft 固有の仕様**

次の構文では、 **try finally**ステートメントについて説明します。

> **\_\_やり直し**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;保護されたコード<br/>
> }<br/>
> **\_\_最終的に**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;終了コード<br/>
> }

## <a name="grammar"></a>文法

*try-finally-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **\_\_お試しください** *複合ステートメント* **\_\_最後に** *複合ステートメント*

**Try-catch**ステートメントは、コードのブロックの実行が中断されC++た場合に、対象アプリケーションがクリーンアップコードの実行を保証できるようにする、C および言語に対する Microsoft の拡張機能です。 クリーンアップは、メモリを解放する、ファイルを閉じる、ファイル ハンドルを解放するなどのタスクで構成されます。 **Try-catch**ステートメントは、ルーチンからの予期しない戻りが発生する可能性があるエラーに対してチェックが行われる複数の場所を持つルーチンで特に便利です。

関連情報とコードサンプルについては、「 [try-Except ステートメント](../cpp/try-except-statement.md)」を参照してください。 構造化例外処理全般の詳細については、「[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)」を参照してください。 /Cli を使用したC++マネージアプリケーションでの例外処理の詳細については、「 [/Clr での例外処理](../extensions/exception-handling-cpp-component-extensions.md)」を参照してください。

> [!NOTE]
> 構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、特に C++ 用にデザインされたものではありません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 プログラムC++については、 C++例外処理機構 ([try、catch、および throw](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント) を使用することをお勧めします。

後の複合ステートメント、 **__try**句は、保護されたセクションです。 後の複合ステートメント、 **__finally**句は、終了ハンドラー。 ハンドラーは、保護されたセクションが例外によって終了 (異常終了) したか、標準的なフォール スルー (正常終了) で終了したかにかかわらず、保護されたセクションが終了したときに実行する一連の操作を指定します。

コントロールに達すると、 **__try**単純な順次実行 (フォール スルー) によってステートメント。 コントロールに入ったとき、 **__try**、その関連付けられたハンドラーがアクティブになります。 制御のフローが try ブロックの終わりに到達すると、次のように実行は処理されます。

1. 終了ハンドラーが呼び出されます。

1. 後に実行が続行、終了ハンドラーが完了したら、 **__finally**ステートメント。 保護されたセクションがどのように終了するかに関係なく (たとえば、保護された本体または**return**ステートメントからの**goto**を使用して)、制御フローが保護されたセクションから移動*する前に*終了ハンドラーが実行されます。

   **__finally**ステートメントは、適切な例外ハンドラーの検索をブロックしません。

例外が発生した場合、 **__try**ブロック、例外のハンドラーを見つける必要があります、オペレーティング システムまたはプログラムは失敗します。 ハンドラーが見つかった場合、すべて **__finally**ブロックが実行され、ハンドラーの実行が再開します。

たとえば、次の図に示すように、一連の関数呼び出しで、関数 A を関数 D にリンクするとします。 各関数には、1 つの終了ハンドラーがあります。 関数 D で例外が発生し、で処理された場合、システムがスタックをアンワインドするときに、終了ハンドラーがこの順序で呼び出されます。D、C、B。

![終了ハンドラー実行&#45;の終了ハンドラー実行順序の順序](../cpp/media/vc38cx1.gif "&#45;") <br/>
終了順序 - ハンドラーの実行

> [!NOTE]
> Try-finally の動作は、など、 **finally**の使用をサポートする他の言語とC#は異なります。  1 つ **__try**の両方ではなくが、必要があります **__finally**と **__except**します。  両方を一緒に使用する場合は、外側の try-except ステートメントで内側の try-finally ステートメントを囲む必要があります。  各ブロックがいつ実行されるかを指定する規則も異なります。

以前のバージョンとの互換性のため **_try**、 **_finally**、および **_leave**のシノニムで **__try**、 **__最後に**と **__leave**しない限り、コンパイラ オプション[/Za\(言語拡張機能を無効にする)](../build/reference/za-ze-disable-language-extensions.md)を指定します。

## <a name="the-__leave-keyword"></a>__leave キーワード

**__Leave**キーワードの保護されたセクション内でのみ有効ですが、 **、try-finally**ステートメント、およびその効果、保護されたセクションの末尾に移動することです。 実行は、終了ハンドラーの最初のステートメントに移って続行されます。

**Goto**ステートメントは、保護されたセクションからジャンプすることもできますが、スタックアンワインドを呼び出すため、パフォーマンスが低下します。 **__Leave**スタック アンワインドが発生しないために、ステートメントが効率的です。

## <a name="abnormal-termination"></a>異常終了

[Longjmp](../c-runtime-library/reference/longjmp.md)ランタイム関数を使用して、 **finally**ステートメントを終了すると、異常終了と見なされます。 移動することはできません、 **__try**ステートメントがジャンプして出る 1 つ。 すべて **__finally**出発点間アクティブであるステートメント (の正常終了、 **__try**ブロック) と変換先 (、 **__except**ブロックします。例外のハンドル) 実行する必要があります。 これは、ローカル アンワインドと呼ばれます。

**Try**ブロックが、ブロックからのジャンプを含め、何らかの理由で途中で終了した場合、スタックをアンワインドするプロセスの一部として、関連付けられている**finally**ブロックが実行されます。 このような場合、 [Abnormaltermination](/windows/win32/Debug/abnormaltermination)関数は、 **finally**ブロック内から呼び出されると**true**を返します。それ以外の場合は**false**を返します。

**Finally**ステートメントの実行中にプロセスが強制終了した場合、終了ハンドラーは呼び出されません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[終了ハンドラーの構文](/windows/win32/Debug/termination-handler-syntax)