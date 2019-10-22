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
ms.openlocfilehash: 4555690476bc149687c680fc2baae53b96658a4e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498494"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

構造化例外処理 (SEH) は、ハードウェア障害などの特定の例外コードの状況を適切に処理するための、C に対する Microsoft の拡張機能です。 Windows と Microsoft C++では SEH がサポートされていますが、 C++ ISO 標準の例外処理を使用することをお勧めします。これにより、コードの移植性と柔軟性が向上します。 ただし、既存のコードまたは特定の種類のプログラムを維持するために、SEH を使用する必要がある場合もあります。

**Microsoft 固有の仕様:**

## <a name="grammar"></a>文法

*try-except ステートメント*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__except** **(** *expression* **)** *compound-statement*

*try-finally ステートメント*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *複合ステートメント* **__finally** *複合ステートメント*

## <a name="remarks"></a>Remarks

SEH を使用すると、実行が予期せず終了した場合に、メモリブロックやファイルなどのリソースが正しく解放されるようにすることができます。 **Goto**ステートメントやリターンコードの詳細なテストに依存しない簡潔な構造化コードを使用して、メモリ不足などの特定の問題を処理することもできます。

ここで説明する try-except および try-finally ステートメントは C 言語に対する Microsoft の拡張機能です。 これらは、イベント後にプログラムの制御をアプリケーションが取得するようにし、そうでない場合は実行を終了させることによって SEH をサポートします。 SEH は C++ ソース ファイルと連携しますが、C++ 向けに設計されていません。 [/Eha または/ehsc](../build/reference/eh-exception-handling-model.md)オプションをC++使用してコンパイルしたプログラムで SEH を使用する場合、ローカルオブジェクトのデストラクターが呼び出されますが、その他の実行動作は期待どおりではない可能性があります。 図については、この記事の後半の例を参照してください。 ほとんどの場合、SEH ではなく、ISO 標準C++ [ C++の例外処理](../cpp/try-throw-and-catch-statements-cpp.md)を使用することをお勧めします。これは、Microsoft コンパイラでもサポートされています。 C++ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。

SEH を使用する C コードがある場合は、例外処理をC++使用C++するコードと組み合わせることができます。 詳細については、「 [」 C++の構造化例外の処理に](../cpp/exception-handling-differences.md)関する説明を参照してください。

SEH メカニズムには次の 2 つがあります。

- 例外[ハンドラー](../cpp/writing-an-exception-handler.md)、または例外に応答したり無視したりできる **__except**ブロック。

- [終了ハンドラー](../cpp/writing-a-termination-handler.md)、または、例外によって終了が発生したかどうかにかかわらず、常に呼び出される **__finally**ブロック。

これら 2 種類のハンドラーは区別されますが、"スタックのアンワインド" というプロセスを通じて密接に関係しています。 構造化例外が発生すると、Windows は現在アクティブな例外ハンドラーを検索します。 ハンドラーは、次の 3 つのうちの 1 つを行うことができます。

- 例外の認識に失敗し、他のハンドラーに制御を渡す。

- 例外を認識し、拒絶する。

- 例外を認識し、処理する。

例外を認識する例外ハンドラーは、例外が発生したときに実行中だった関数内にない場合があります。 場合によっては、スタックのかなり上位の関数内にあります。 現在実行中の関数と、スタック フレーム上の他のすべての関数が終了します。 この処理中、スタックは "アンワインド" されます。つまり、終了した関数のローカルの非静的変数はスタックから消去されます。

これがスタックをアンワインドするため、オペレーティング システムは、各関数に書き込んだ終了ハンドラーを呼び出します。 終了ハンドラーを使用して、異常終了のために開いたままになっているリソースをクリーンアップできます。 クリティカルセクションを入力した場合は、終了ハンドラーで終了できます。 プログラムがシャットダウンする場合、一時ファイルを閉じたり削除するなどの他のハウスキーピング タスクを実行できます。

## <a name="next-steps"></a>次の手順

- [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)

- [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)

- [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)

## <a name="example"></a>例

前述のように、 C++プログラムで SEH を使用し、 **/Eha**または **/ehsc**オプションを使用してコンパイルすると、ローカルオブジェクトのデストラクターが呼び出されます。 ただし、C++ 例外も使用している場合は、実行時の動作は予期したとおりにならない可能性があります。 この例では、これらの動作の違いを示します。

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

**/Ehsc**を使用してこのコードをコンパイルするが、ローカルテスト`CPPEX`コントロールマクロが定義されていない`TestClass`場合、デストラクターは実行されず、出力は次のようになります。

```Output
Triggering SEH exception
Executing SEH __except block
```

**/Ehsc**を使用してコードをコンパイルし`CPPEX` 、 C++ (例外が`/DCPPEX`スローされるように) を使用して`TestClass`定義されている場合、デストラクターが実行され、出力は次のようになります。

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

**/Eha**を使用してコードをコンパイルする場合`TestClass` 、デストラクターは、またはを使用`std::throw`して例外がスローされたかどうかに関係なく実行さ`CPPEX`れます。または、例外をトリガーするために SEH を使用します。 出力は次のようになります。

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
[エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[構造化例外処理 (Windows)](/windows/win32/debug/structured-exception-handling)
