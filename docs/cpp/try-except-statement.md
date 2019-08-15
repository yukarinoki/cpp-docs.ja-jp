---
title: try-except ステートメント
ms.date: 10/09/2018
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- _except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: b4dccb58bf63f51e88006b793b8a94bfbe021c73
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400547"
---
# <a name="try-except-statement"></a>try-except ステートメント

**Microsoft 固有の仕様**

**try-except** ステートメントは C に対する Microsoft 拡張機能であり、構造化例外処理の C++ 言語をサポートします。

## <a name="syntax"></a>構文

> **\_\_try**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;保護されたコード<br/>
> }<br/>
> **\_\_except** ( *expression* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;例外ハンドラーのコード<br/>
> }

## <a name="remarks"></a>Remarks

**try-except** ステートメントは C に対する Microsoft 拡張機能であり、C++ 言語を取得する対象アプリケーションをできるようにするプログラムの実行を正常に終了するイベントが発生したときを制御します。 このようなイベントが呼び出されます*例外*、例外を処理するメカニズムを呼び出すと*例外処理を構造化*(SEH)。

関連情報については、[try-finally ステートメント](../cpp/try-finally-statement.md)を参照してください。

例外は、ハードウェア例外またはソフトウェア例外です。 アプリケーションがハードウェア例外またはソフトウェア例外から完全に回復できない場合でも、構造化例外処理はエラー情報を表示し、問題の診断に役立つアプリケーションの内部状態をトラップすることができます。 これは、簡単に再現できない断続的な問題の場合に特に便利です。

> [!NOTE]
> 構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、特に C++ 用にデザインされたものではありません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 C++ プログラムは、お勧め、C++ 例外処理機構を使用すること ([try、catch、および throw](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント)。

後の複合ステートメント、 **__try**句は、本体または保護されたセクションです。 後の複合ステートメント、 **__except**句は、例外ハンドラー。 ハンドラーは、保護されたセクションの本体の実行中に例外が発生した場合に行われる一連の操作を指定します。 次のように実行されます。

1. 保護されたセクションが実行されます。

1. 実行は、ステートメントの後で続行、保護されたセクションの実行中に例外が発生しない場合、 **__except**句。

1. 保護されたセクションの実行中に例外が発生したか、保護されたセクションを呼び出す任意のルーチンで、 **__except** *式*(と呼ばれる、*フィルター*式)評価し、値が例外の処理方法を決定します。 指定できる値は 3 つあります。

   - EXCEPTION_CONTINUE_EXECUTION (-1) の例外が閉じられます。 例外が発生した位置から実行を継続します。

   - EXCEPTION_CONTINUE_SEARCH (0) の例外が認識されていません。 最初に **try-except** ステートメントを含むハンドラーを検索してから、次に優先順位が最も高いハンドラーについてスタックを検索し続けます。

   - EXCEPTION_EXECUTE_HANDLER (1) の例外が認識されました。 実行によって例外ハンドラーに制御を移動、 **__except**複合ステートメントの後の実行を続行し、 **__except**ブロックします。

**__Except**式は C の式として評価される、単一の値を条件式演算子、またはコンマ演算子に制限されます。 より広範な処理が必要な場合、前に挙げた 3 つの値の 1 つを返すルーチンを式で呼び出すことができます。

各アプリケーションが独自の例外ハンドラーを持つ場合があります。

移動することはできません、 **__try**ステートメントを 1 つからのジャンプは無効です。 実行中のプロセスが終了した場合、例外ハンドラーは呼び出されませんが、**try-except**ステートメント。

以前のバージョンとの互換性のため **_try**、 **_except**、および **_leave**のシノニムで **__try**、 **__except**と **__leave**しない限り、コンパイラ オプション[/Za\(言語拡張機能を無効にする)](../build/reference/za-ze-disable-language-extensions.md)を指定します。

### <a name="the-leave-keyword"></a>__leave キーワード

**__Leave**キーワードの保護されたセクション内でのみ有効ですが、**try-except**ステートメントとその効果は、保護されたセクションの末尾に移動します。 実行は、例外ハンドラーの後の最初のステートメントから続行されます。

A **goto**ステートメントは、保護されたセクションからも進んでし、同様に、パフォーマンスは低下しません、 **try-finally**ステートメント スタック アンワインドが発生しないためです。 使用すること勧めただし、 **__leave**キーワードではなく**goto**ステートメントは、保護されたセクションが大規模または複雑な場合は、プログラミングの間違いを犯すことが少なくするためです。

### <a name="structured-exception-handling-intrinsic-functions"></a>構造化例外処理の組み込み関数

構造化例外処理で使用できるは 2 つの組み込み関数を提供する、**try-except*ステートメント:`GetExceptionCode`と`GetExceptionInformation`します。

`GetExceptionCode` 例外のコード (32 ビット整数) を返します。

組み込み関数`GetExceptionInformation`例外に関する追加情報を含む構造体へのポインターを返します。 このポインターを使用して、ハードウェア例外のときに存在していたコンピューターの状態にアクセスできます。 構造は、次のとおりです。

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

ポインター型`PEXCEPTION_RECORD`と`PCONTEXT`インクルード ファイルで定義されて\<winnt.h >、および`_EXCEPTION_RECORD`と`_CONTEXT`インクルード ファイルで定義されて\<excpt.h >

使用することができます`GetExceptionCode`例外ハンドラー内で。 ただし、使用することができます`GetExceptionInformation`例外フィルター式内でのみです。 これが示す情報は、一般的にスタックにあり、制御が例外ハンドラーに移されると使用できなくなります。

組み込み関数`AbnormalTermination`は終了ハンドラー内で使用できます。 場合は、0 を返しますの本文、 **try-finally**ステートメントが順次終了します。 その他の場合は、1 を返します。

excpt.h では、これらの組み込みの代替名を定義します。

`GetExceptionCode` 等価します。 `_exception_code`

`GetExceptionInformation` 等価します。 `_exception_info`

`AbnormalTermination` 等価します。 `_abnormal_termination`

## <a name="example"></a>例

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>出力

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
