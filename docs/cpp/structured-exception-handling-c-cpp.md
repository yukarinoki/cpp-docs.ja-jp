---
title: Structured Exception Handling (C/C++)
ms.date: 08/14/2018
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 942a7e48e4315454476bfe93c68169f461b006b2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245123"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

Structured exception handling (SEH) is a Microsoft extension to C to handle certain exceptional code situations, such as hardware faults, gracefully. Although Windows and Microsoft C++ support SEH, we recommend that you use ISO-standard C++ exception handling because it makes your code more portable and flexible. Nevertheless, to maintain existing code or for particular kinds of programs, you still might have to use SEH.

**Microsoft specific:**

## <a name="grammar"></a>文法

*try-except-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__except** **(** *expression* **)** *compound-statement*

*try-finally-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *複合ステートメント* **__finally** *複合ステートメント*

## <a name="remarks"></a>Remarks

With SEH, you can ensure that resources such as memory blocks and files are released correctly if execution unexpectedly terminates. You can also handle specific problems—for example, insufficient memory—by using concise structured code that does not rely on **goto** statements or elaborate testing of return codes.

ここで説明する try-except および try-finally ステートメントは C 言語に対する Microsoft の拡張機能です。 これらは、イベント後にプログラムの制御をアプリケーションが取得するようにし、そうでない場合は実行を終了させることによって SEH をサポートします。 SEH は C++ ソース ファイルと連携しますが、C++ 向けに設計されていません。 If you use SEH in a C++ program that you compile by using the [/EHa or /EHsc](../build/reference/eh-exception-handling-model.md) option, destructors for local objects are called but other execution behavior might not be what you expect. For an illustration, see the example later in this article. In most cases, instead of SEH we recommend that you use ISO-standard [C++ exception handling](../cpp/try-throw-and-catch-statements-cpp.md), which the Microsoft C++ compiler also supports. C++ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。

If you have C code that uses SEH, you can mix it with C++ code that uses C++ exception handling. For information, see [Handle structured exceptions in C++](../cpp/exception-handling-differences.md).

SEH メカニズムには次の 2 つがあります。

- [Exception handlers](../cpp/writing-an-exception-handler.md), or **__except** blocks, which can respond to or dismiss the exception.

- [Termination handlers](../cpp/writing-a-termination-handler.md), or **__finally** blocks, which are always called, whether an exception causes termination or not.

これら 2 種類のハンドラーは区別されますが、"スタックのアンワインド" というプロセスを通じて密接に関係しています。 When a structured exception occurs, Windows looks for the most recently installed exception handler that is currently active. ハンドラーは、次の 3 つのうちの 1 つを行うことができます。

- 例外の認識に失敗し、他のハンドラーに制御を渡す。

- 例外を認識し、拒絶する。

- 例外を認識し、処理する。

例外を認識する例外ハンドラーは、例外が発生したときに実行中だった関数内にない場合があります。 場合によっては、スタックのかなり上位の関数内にあります。 現在実行中の関数と、スタック フレーム上の他のすべての関数が終了します。 During this process, the stack is "unwound;" that is, local non-static variables of terminated functions are cleared from the stack.

これがスタックをアンワインドするため、オペレーティング システムは、各関数に書き込んだ終了ハンドラーを呼び出します。 終了ハンドラーを使用して、異常終了のために開いたままになっているリソースをクリーンアップできます。 If you've entered a critical section, you can exit it in the termination handler. プログラムがシャットダウンする場合、一時ファイルを閉じたり削除するなどの他のハウスキーピング タスクを実行できます。

## <a name="next-steps"></a>次のステップ

- [Writing an exception handler](../cpp/writing-an-exception-handler.md)

- [Writing a termination handler](../cpp/writing-a-termination-handler.md)

- [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)

## <a name="example"></a>例

As stated earlier, destructors for local objects are called if you use SEH in a C++ program and compile it by using the **/EHa** or **/EHsc** option. ただし、C++ 例外も使用している場合は、実行時の動作は予期したとおりにならない可能性があります。 This example demonstrates these behavioral differences.

```cpp
#include <stdio.h>
#include <Windows.h>
#include <exception>

class TestClass
{
public:
    ~TestClass()
    {
        printf("Destroying TestClass!\r\n");
    }
};

__declspec(noinline) void TestCPPEX()
{
#ifdef CPPEX
    printf("Throwing C++ exception\r\n");
    throw std::exception("");
#else
    printf("Triggering SEH exception\r\n");
    volatile int *pInt = 0x00000000;
    *pInt = 20;
#endif
}

__declspec(noinline) void TestExceptions()
{
    TestClass d;
    TestCPPEX();
}

int main()
{
    __try
    {
        TestExceptions();
    }
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf("Executing SEH __except block\r\n");
    }

    return 0;
}
```

If you use **/EHsc** to compile this code but the local test control macro `CPPEX` is undefined, there is no execution of the `TestClass` destructor and the output looks like this:

```Output
Triggering SEH exception
Executing SEH __except block
```

If you use **/EHsc** to compile the code and `CPPEX` is defined by using `/DCPPEX` (so that a C++ exception is thrown), the `TestClass` destructor executes and the output looks like this:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

If you use **/EHa** to compile the code, the `TestClass` destructor executes regardless of whether the exception was thrown by using `std::throw` or by using SEH to trigger the exception, that is, whether `CPPEX` defined or not. 出力は次のようになります。

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

詳細については、「[/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[例外処理](../cpp/exception-handling-in-visual-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
[Errors and Exception Handling](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Structured Exception Handling (Windows)](/windows/win32/debug/structured-exception-handling)
