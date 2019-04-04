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
ms.openlocfilehash: b77a218340399578e3c9428100476787e2e60b25
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534564"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

構造化例外処理 (SEH) は、ハードウェアの障害などの特定のコードを例外的な状況を適切に処理するために C# の Microsoft 拡張機能です。 Windows および Visual C は SEH をサポートよりポータブルで柔軟なコードがあるために、ISO 標準 C++ の例外処理を使用することをお勧めします。 ただし、既存のコードを維持するために特定の種類のプログラムでは、まだ必要があります SEH を使用するか。

**Microsoft 固有:**

## <a name="grammar"></a>文法

*try-ステートメントを除く*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _try** *複合ステートメント* **_ _except** **(** *式* **)** *複合ステートメント*

*try-最後に、ステートメント*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _try** *複合ステートメント* **_ _finally** *複合ステートメント*

## <a name="remarks"></a>Remarks

Seh を使うと、実行が予期せず終了した場合にメモリ ブロックやファイルなどのリソースが正しく解放されることを確認できます。 特定の問題を処理することもできます。-メモリの不足など — に依存しない簡潔の構造化されたコードを使用して**goto**ステートメントやリターン コードの複雑なテスト。

ここで説明する try-except および try-finally ステートメントは C 言語に対する Microsoft の拡張機能です。 これらは、イベント後にプログラムの制御をアプリケーションが取得するようにし、そうでない場合は実行を終了させることによって SEH をサポートします。 SEH は C++ ソース ファイルと連携しますが、C++ 向けに設計されていません。 使用してコンパイルする C++ プログラムで SEH を使用するかどうか、 [/EHa または/EHsc](../build/reference/eh-exception-handling-model.md)オプションの場合は、ローカル オブジェクトと呼ばれますが、その他の実行動作が期待どおりではないデストラクター。 例については、この記事の後半の例を参照してください。 ほとんどの場合、SEH の代わりに勧め ISO 標準を使用する[C++ 例外処理](../cpp/try-throw-and-catch-statements-cpp.md)、Visual C もサポートします。 C++ 例外処理を使用すると、コードの移植性が高くなり、すべての種類の例外を処理できるようになります。

SEH を使用する C# コードを使っている場合は、C++ 例外処理を使用する C++ コードと混在させることができます。 詳しくは、[C++ で構造化例外処理](../cpp/exception-handling-differences.md)を参照してください。

SEH メカニズムには次の 2 つがあります。

- [例外ハンドラー](../cpp/writing-an-exception-handler.md)、または **_ _except**ブロックに応答したり、例外を無視することができます。

- [終了ハンドラー](../cpp/writing-a-termination-handler.md)、または **_ _finally**は常に呼び出されると、かどうか、例外によって終了するかどうか、ブロックします。

これら 2 種類のハンドラーは区別されますが、"スタックのアンワインド" というプロセスを通じて密接に関係しています。 構造化例外が発生したときに、Windows は、現在アクティブになっている最近インストールされた例外ハンドラーを検索します。 ハンドラーは、次の 3 つのうちの 1 つを行うことができます。

- 例外の認識に失敗し、他のハンドラーに制御を渡す。

- 例外を認識し、拒絶する。

- 例外を認識し、処理する。

例外を認識する例外ハンドラーは、例外が発生したときに実行中だった関数内にない場合があります。 場合によっては、スタックのかなり上位の関数内にあります。 現在実行中の関数と、スタック フレーム上の他のすべての関数が終了します。 このプロセス中に、スタックが「アンワインド;」は、終了した関数のローカルの非静的変数がスタックから消去は。

これがスタックをアンワインドするため、オペレーティング システムは、各関数に書き込んだ終了ハンドラーを呼び出します。 終了ハンドラーを使用して、異常終了のために開いたままになっているリソースをクリーンアップできます。 クリティカル セクションを入力した場合は、終了ハンドラーで終了できます。 プログラムがシャットダウンする場合、一時ファイルを閉じたり削除するなどの他のハウスキーピング タスクを実行できます。

## <a name="next-steps"></a>次の手順

- [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)

- [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)

- [C++ での構造化例外の処理](../cpp/exception-handling-differences.md)

## <a name="example"></a>例

既に説明したとおり、デストラクターの場合は、C++ プログラムで SEH を使用してを使用してコンパイルし、ローカルのオブジェクトが呼び出されます、 **/EHa**または **/EHsc**オプション。 ただし、C++ 例外も使用している場合は、実行時の動作は予期したとおりにならない可能性があります。 この例では、これらの動作の違いを示します。

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

使用する場合 **/EHsc**このコードがローカル テスト コントロール マクロをコンパイルする`CPPEX`が未定義の場合がありますの実行はされず、`TestClass`デストラクターと出力は次のように。

```Output
Triggering SEH exception
Executing SEH __except block
```

使用する場合 **/EHsc**コードをコンパイルして`CPPEX`によって定義されている`/DCPPEX`(C++ 例外をスロー) するため、`TestClass`デストラクターが実行され、出力は次のようになります。

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

使用する場合 **/EHa** 、コードをコンパイルする、`TestClass`デストラクターの実行を使用して例外がスローされたかどうかに関係なく`std::throw`または SEH を使用して、例外をトリガーするかどうか`CPPEX`定義またはじゃない。 出力は次のようになります。

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
[構造化例外処理 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)
