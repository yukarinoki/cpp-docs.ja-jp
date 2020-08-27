---
title: Structured Exception Handling (C/C++)
description: Microsoft C/c + + での構造化例外処理の概要について説明します。
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 142e89bc82adbe7938e8825029908e814df6055c
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898637"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

構造化例外処理 (SEH) は、ハードウェア障害などの特定の例外コードの状況を適切に処理するための、C に対する Microsoft の拡張機能です。 Windows と Microsoft C++ は SEH をサポートしていますが、ISO 標準の C++ 例外処理を使用することをお勧めします。 これにより、コードの移植性と柔軟性が向上します。 ただし、既存のコードまたは特定の種類のプログラムを維持するために、SEH を使用する必要がある場合もあります。

**Microsoft 固有:**

## <a name="grammar"></a>文法

> *`try-except-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__except`** **`(`** *`expression`* **`)`** *`compound-statement`*
>
> *`try-finally-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

## <a name="remarks"></a>注釈

SEH を使用すると、実行が予期せず終了した場合に、メモリブロックやファイルなどのリソースが正しく解放されるようにすることができます。 また、 **`goto`** ステートメントやリターンコードの詳細なテストに依存しない簡潔な構造化コードを使用して、メモリ不足などの特定の問題を処理することもできます。

`try-except` `try-finally` この記事で参照されるおよびステートメントは、C 言語に対する Microsoft の拡張機能です。 これらは、イベント後にプログラムの制御をアプリケーションが取得するようにし、そうでない場合は実行を終了させることによって SEH をサポートします。 SEH は C++ ソース ファイルと連携しますが、C++ 向けに設計されていません。 [ `/EHa` または `/EHsc` ](../build/reference/eh-exception-handling-model.md)オプションを使用してコンパイルした C++ プログラムで SEH を使用する場合、ローカルオブジェクトのデストラクターが呼び出されますが、他の実行動作が予期したものと異なる可能性があります。 図については、この記事の後半の例を参照してください。 ほとんどの場合、SEH ではなく、ISO 標準の [C++ 例外処理](../cpp/try-throw-and-catch-statements-cpp.md)を使用することをお勧めします。これは、Microsoft c++ コンパイラでもサポートされています。 C++ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。

SEH を使用する C コードがある場合は、C++ 例外処理を使用する C++ コードと組み合わせることができます。 詳細については、「 [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)」を参照してください。

SEH メカニズムには次の 2 つがあります。

- 例外[ハンドラー](../cpp/writing-an-exception-handler.md)、または **`__except`** 例外に対して応答または破棄できるブロック。

- [終了ハンドラー](../cpp/writing-a-termination-handler.md)(または **`__finally`** ブロック)。例外によって終了が発生したかどうかにかかわらず、常に呼び出されます。

この2種類のハンドラーは区別されますが、 *スタックのアンワインド*と呼ばれるプロセスによって密接に関連しています。 構造化例外が発生すると、Windows は現在アクティブな例外ハンドラーを検索します。 ハンドラーは、次の 3 つのうちの 1 つを行うことができます。

- 例外の認識に失敗し、他のハンドラーに制御を渡す。

- 例外を認識し、拒絶する。

- 例外を認識し、処理する。

例外を認識する例外ハンドラーは、例外が発生したときに実行中だった関数内にない場合があります。 スタック上の関数の方がはるかに高い場合もあります。 現在実行中の関数と、スタック フレーム上の他のすべての関数が終了します。 このプロセスでは、スタックは *アンワインド*されます。 つまり、終了した関数のローカルの非静的変数はスタックからクリアされます。

これがスタックをアンワインドするため、オペレーティング システムは、各関数に書き込んだ終了ハンドラーを呼び出します。 終了ハンドラーを使用すると、異常終了のために開いたままになっているリソースをクリーンアップできます。 クリティカルセクションを入力した場合は、終了ハンドラーで終了できます。 プログラムをシャットダウンするときに、一時ファイルの終了や削除など、その他のハウスキーピングタスクを実行できます。

## <a name="next-steps"></a>次のステップ

- [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)

- [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)

- [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)

## <a name="example"></a>例

前述のように、C++ プログラムで SEH を使用し、またはオプションを使用してコンパイルすると、ローカルオブジェクトのデストラクターが呼び出され **`/EHa`** **`/EHsc`** ます。 ただし、C++ 例外も使用している場合は、実行中の動作が期待どおりではない可能性があります。 この例では、これらの動作の違いを示します。

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

を使用し **`/EHsc`** てこのコードをコンパイルしても、ローカルテストコントロールマクロが定義されていない場合、 `CPPEX` デストラクターは実行され `TestClass` ません。 出力は次のようになります。

```Output
Triggering SEH exception
Executing SEH __except block
```

を使用して **`/EHsc`** コードをコンパイルし、 `CPPEX` `/DCPPEX` (C++ 例外がスローされるように) を使用して定義されている場合、デストラクターが実行され、出力は次のようになり `TestClass` ます。

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

を使用してコードをコンパイルした場合 **`/EHa`** 、 `TestClass` デストラクターはまたはを使用して例外がスローされたかどうかを実行し、 `std::throw` 例外をトリガーするために SEH を使用します。 つまり、が定義されているかどうかを示し `CPPEX` ます。 出力は次のようになります。

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

詳細については、「 [ `/EH` (例外処理モデル)](../build/reference/eh-exception-handling-model.md)」を参照してください。

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[例外処理](../cpp/exception-handling-in-visual-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[`<exception>`](../standard-library/exception.md)<br/>
[エラーと例外処理](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[構造化例外処理 (Windows)](/windows/win32/debug/structured-exception-handling)
