---
title: try-except ステートメント
description: __tryと構造化例外処理ステートメントへの Microsoft C++ __except参照。
ms.date: 04/03/2020
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- _exception_info
- __except
- _except
- _exception_code
- __except_cpp
- _exception_info_cpp
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
ms.openlocfilehash: 132edf7cc9819637fafa3947686972d311924b99
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366234"
---
# <a name="try-except-statement"></a>try-except ステートメント

**try-except**ステートメントは、C 言語および C++ 言語での構造化例外処理をサポートする Microsoft 拡張機能です。 この拡張機能は **、マイクロソフト固有の**.

## <a name="syntax"></a>構文

> **\_\_試す**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;保護されたコード<br/>
> }<br/>
> 除く (*式*) ** \_ \_**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;例外ハンドラコード<br/>
> }

## <a name="remarks"></a>解説

**try-except**ステートメントは、C 言語と C++ 言語に対するマイクロソフトの拡張機能です。 通常はプログラムの実行を終了するイベントが発生したときに、ターゲット アプリケーションが制御を取得できるようにします。 このようなイベントは*構造化例外*と*呼ばれます。* これらの例外を処理するメカニズムは、*構造化例外処理*(SEH) と呼ばれます。

関連情報については、 [try-finally ステートメント](../cpp/try-finally-statement.md)を参照してください。

例外は、ハードウェア ベースまたはソフトウェア ベースのいずれかです。 構造化例外処理は、アプリケーションがハードウェアまたはソフトウェアの例外から完全に回復できない場合でも役立ちます。 SEH は、エラー情報を表示し、アプリケーションの内部状態をトラップして問題の診断に役立てるようにします。 再現が容易ではない断続的な問題に特に役立ちます。

> [!NOTE]
> 構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、C++ 用に設計されたものではありません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 C++ プログラムの場合は、ネイティブ C++ 例外処理 ( [try ステートメント、catch ステートメント、および throw](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント ) を使用することをお勧めします。

**__try**節の後の複合ステートメントは、*本体*または*保護セクションです*。 **__except**式は *、フィルター*式とも呼ばれます。 その値によって、例外の処理方法が決まります。 **__except**節の後の複合ステートメントは、例外ハンドラーです。 ハンドラーは、body セクションの実行中に例外が発生した場合に実行するアクションを指定します。 次のように実行されます。

1. 保護されたセクションが実行されます。

1. 保護されたセクションの実行中に例外が発生しない場合 **、__except**節の後のステートメントで実行が続行されます。

1. 保護されたセクションの実行中、または保護されたセクションが呼び出すルーチンで例外が発生した場合 **、__except**式が評価されます。 指定可能な 3 つの値は次のとおりです。

   - `EXCEPTION_CONTINUE_EXECUTION`(-1)例外は解除されます。 例外が発生した位置から実行を継続します。

   - `EXCEPTION_CONTINUE_SEARCH`(0) 例外が認識されない。 最初に **try-except** ステートメントを含むハンドラーを検索してから、次に優先順位が最も高いハンドラーについてスタックを検索し続けます。

   - `EXCEPTION_EXECUTE_HANDLER`(1) 例外が認められる。 **__except**複合ステートメントを実行して例外ハンドラーに制御を移し **、__except**ブロックの後に実行を続行します。

**__except**式は C 式として評価されます。 これは、単一の値、条件式演算子、またはコンマ演算子に制限されます。 より広範な処理が必要な場合、前に挙げた 3 つの値の 1 つを返すルーチンを式で呼び出すことができます。

各アプリケーションが独自の例外ハンドラーを持つ場合があります。

**__try**ステートメントにジャンプするのは無効ですが、ステートメントから飛び出すのは有効です。 **try-except**ステートメントの実行中にプロセスが終了した場合、例外ハンドラーは呼び出されません。

以前のバージョンとの互換性を保つ**には、コンパイラ**オプション[/Za\(を無効にする言語拡張)](../build/reference/za-ze-disable-language-extensions.md)を指定しない限り、 _try 、 **_except**、 および **_leave**は **__try**、 **__except、****および __leave**の同義語です。

### <a name="the-__leave-keyword"></a>__leave キーワード

**__leave**キーワードは**try-except**ステートメントの保護されたセクション内でのみ有効であり、その効果は、保護されたセクションの末尾にジャンプします。 実行は、例外ハンドラーの後の最初のステートメントから続行されます。

**goto**ステートメントは、保護されたセクションから飛び出す可能性があり **、try-finally**ステートメントのようにパフォーマンスが低下することはありません。 スタックのアンワインドが発生しないためです。 ただし **、goto**ステートメントではなく **__leave**キーワードを使用することをお勧めします。 その理由は、保護されたセクションが大きいか複雑な場合にプログラミングミスを犯す可能性が低いためです。

### <a name="structured-exception-handling-intrinsic-functions"></a>構造化例外処理の組み込み関数

構造化例外処理は **、try except**ステートメントで使用できる 2 つの組み込み関数を提供[GetExceptionInformation](/windows/win32/Debug/getexceptioninformation)[します。](/windows/win32/Debug/getexceptioncode)

`GetExceptionCode`は、例外のコード (32 ビット整数) を返します。

組み込`GetExceptionInformation`み関数は、例外に関する追加情報を含む[EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers)構造体へのポインターを返します。 このポインターを使用して、ハードウェア例外のときに存在していたコンピューターの状態にアクセスできます。 構造は次のとおりです。

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

ポインターの型`PEXCEPTION_RECORD`と`PCONTEXT`インクルード\<ファイル winnt.h>で`_EXCEPTION_RECORD`定義され`_CONTEXT`、インクルード ファイル\<excpt.h>

例外ハンドラー内`GetExceptionCode`で使用できます。 ただし、例外フィルター式`GetExceptionInformation`内でのみ使用できます。 この情報が指す情報は、通常スタック上にあり、コントロールが例外ハンドラーに転送されるときには使用できなくなります。

組み込み関数[異常終了](/windows/win32/Debug/abnormaltermination)は、終了ハンドラ内で使用できます。 **try-finally**ステートメントの本体が連続して終了した場合は 0 を返します。 その他の場合は、1 を返します。

\<excpt.h>は、これらの組み込み用の代替名をいくつか定義します。

`GetExceptionCode` は `_exception_code` と同じです。

`GetExceptionInformation` は `_exception_info` と同じです。

`AbnormalTermination` は `_abnormal_termination` と同じです。

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

## <a name="see-also"></a>関連項目

[例外ハンドラーの作成](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
