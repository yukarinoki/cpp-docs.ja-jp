---
title: try-except ステートメント
description: __Try および __except の構造化例外処理ステートメントへの Microsoft C++ リファレンス。
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
ms.openlocfilehash: d0471bbd50e07fccbf160e9e866de4c545cdeb7e
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825771"
---
# <a name="try-except-statement"></a>try-except ステートメント

**Try-except**ステートメントは、C および C++ 言語の構造化例外処理をサポートする Microsoft 拡張機能です。 この拡張機能は **、Microsoft 固有**のものです。

## <a name="syntax"></a>構文

> **\_\_やり直し**\
> {\
> &nbsp;&nbsp;&nbsp;&nbsp;保護されたコード \
> }\
> except (*式*) \ ** \_ \_**
> {\
> &nbsp;&nbsp;&nbsp;&nbsp;例外ハンドラーコード \
> }

## <a name="remarks"></a>解説

**Try-except**ステートメントは、C および C++ 言語に対する Microsoft の拡張機能です。 これにより、通常はプログラムの実行を終了するイベントが発生したときに、対象アプリケーションで制御できるようになります。 このようなイベントは、*構造化例外*、つまり短い*例外*と呼ばれます。 これらの例外を処理するメカニズムは、*構造化例外処理*(SEH) と呼ばれます。

関連情報については、「 [try finally ステートメント](../cpp/try-finally-statement.md)」を参照してください。

例外は、ハードウェアベースまたはソフトウェアベースのいずれかです。 構造化例外処理は、アプリケーションがハードウェアまたはソフトウェアの例外から完全に回復できない場合でも役立ちます。 SEH を使用すると、エラー情報を表示し、問題の診断に役立つアプリケーションの内部状態をトラップすることができます。 これは、簡単に再現できない断続的な問題に特に役立ちます。

> [!NOTE]
> 構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、特に C++ 向けには設計されていません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 C++ プログラムでは、ネイティブ C++ 例外処理 ( [try、catch、および throw](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント) を使用することをお勧めします。

**__Try**句の後の複合ステートメントは、*本体*または*保護*されたセクションです。 **__Except**式は、*フィルター*式とも呼ばれます。 この値によって、例外の処理方法が決まります。 **__Except**句の後の複合ステートメントは、例外ハンドラーです。 ハンドラーは、本文セクションの実行中に例外が発生した場合に実行するアクションを指定します。 次のように実行されます。

1. 保護されたセクションが実行されます。

1. 保護されたセクションの実行中に例外が発生しなかった場合は、 **__except**句の後のステートメントから実行が続行されます。

1. 保護されたセクションの実行中に例外が発生した場合、または保護されたセクションがを呼び出した場合は、 **__except**式が評価されます。 指定可能な 3 つの値は次のとおりです。

   - `EXCEPTION_CONTINUE_EXECUTION`(-1)例外は破棄されます。 例外が発生した位置から実行を継続します。

   - `EXCEPTION_CONTINUE_SEARCH`(0) 例外が認識されません。 最初に **try-except** ステートメントを含むハンドラーを検索してから、次に優先順位が最も高いハンドラーについてスタックを検索し続けます。

   - `EXCEPTION_EXECUTE_HANDLER`(1) 例外が認識されています。 **__Except**複合ステートメントを実行して例外ハンドラーに制御を移し、 **__except**ブロックの後に実行を継続します。

**__Except**式は、C 式として評価されます。 1つの値、条件式演算子、またはコンマ演算子に制限されています。 より広範な処理が必要な場合、前に挙げた 3 つの値の 1 つを返すルーチンを式で呼び出すことができます。

各アプリケーションが独自の例外ハンドラーを持つ場合があります。

**__Try**ステートメントにジャンプすることはできませんが、1つのステートメントからジャンプすることは有効です。 **Try-except**ステートメントの実行中にプロセスが終了した場合、例外ハンドラーは呼び出されません。

以前のバージョンとの互換性を保つために、 **_try**、 **_except**、および **_leave**は、コンパイラオプションである [[言語\(拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない限り、 **__try**、 **__except**、および **__leave**のシノニムです。

### <a name="the-__leave-keyword"></a>__leave キーワード

**__Leave**キーワードは、 **try-except**ステートメントの保護されたセクション内でのみ有効であり、その結果、保護されたセクションの末尾に移動します。 実行は、例外ハンドラーの後の最初のステートメントから続行されます。

**Goto**ステートメントは、保護されたセクションからジャンプすることもできます。また、 **try finally**ステートメントの場合と同様にパフォーマンスが低下することはありません。 これは、スタックアンワインドが発生しないためです。 ただし、 **goto**ステートメントではなく、 **__leave**キーワードを使用することをお勧めします。 その理由は、保護されたセクションが大規模または複雑な場合にプログラミングの間違いを犯す可能性が低いためです。

### <a name="structured-exception-handling-intrinsic-functions"></a>構造化例外処理の組み込み関数

構造化例外処理には、 **try-except**ステートメントで使用できる2つの組み込み関数 ( [getexceptioncode](/windows/win32/Debug/getexceptioncode)と[getexceptioncode](/windows/win32/Debug/getexceptioninformation)) が用意されています。

`GetExceptionCode`例外のコード (32 ビット整数) を返します。

組み込み関数`GetExceptionInformation`は、例外に関する追加情報を含む[EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers)構造体へのポインターを返します。 このポインターを使用して、ハードウェア例外のときに存在していたコンピューターの状態にアクセスできます。 構造は次のとおりです。

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

ポインター `PEXCEPTION_RECORD`型と`PCONTEXT`はインクルードファイル\<winnt.h> `_EXCEPTION_RECORD`で定義され、および`_CONTEXT`はインクルードファイル\<excpt.h で定義され>

は、例外`GetExceptionCode`ハンドラー内で使用できます。 ただし、は例外フィルター `GetExceptionInformation`式内でのみ使用できます。 参照先の情報は、通常はスタック上にあり、制御が例外ハンドラーに転送されるときには使用できなくなります。

組み込み関数[Abnormaltermination](/windows/win32/Debug/abnormaltermination)は、終了ハンドラー内で使用できます。 **Try finally**ステートメントの本体が連続して終了する場合は、0を返します。 その他の場合は、1 を返します。

\<excpt.h> は、これらの組み込みの代替名を定義します。

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

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
