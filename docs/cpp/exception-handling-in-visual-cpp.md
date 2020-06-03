---
title: MSVC での例外処理
description: C++ 言語リファレンス例外処理の概要。
ms.date: 04/15/2020
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 0d60f49c6f1412925c19aaf497352940411b5d92
ms.sourcegitcommit: 0e4feb35b47c507947262d00349d4a893863a6d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81396278"
---
# <a name="exception-handling-in-msvc"></a>MSVC での例外処理

例外とは、プログラムが通常の実行パスに沿って進むことを妨げるエラー状態のことであり、プログラムで制御できない可能性があります。 オブジェクトの作成、ファイル入出力、他のモジュールからの関数呼び出しなど、特定の操作は、プログラムが正しく実行されている場合でも、例外の潜在的な原因となります。 堅牢なコードは例外を予期し、それを処理します。 論理エラーを検出するには、例外ではなくアサーションを使用します ([アサーションの使用を](/visualstudio/debugger/c-cpp-assertions)参照)。

## <a name="kinds-of-exceptions"></a>例外の種類

マイクロソフト C++ コンパイラ (MSVC) は、3 種類の例外処理をサポートしています。

- [C++ 例外処理](errors-and-exception-handling-modern-cpp.md)

   ほとんどの C++ プログラムでは、C++ 例外処理を使用する必要があります。 タイプ セーフで、スタック アンワインド中にオブジェクトデストラクターが呼び出されるようにします。

- [構造化された例外処理](structured-exception-handling-c-cpp.md)

   Windows は、構造化例外処理 (SEH) と呼ばれる独自の例外メカニズムを提供します。 C++ または MFC プログラミングには推奨されません。 SEH は非 MFC C プログラムでのみ使用します。

- [MFC 例外](../mfc/exception-handling-in-mfc.md)

   バージョン 3.0 以降、MFC は C++ 例外を使用しています。 このマクロは、形式の C++ 例外に似た古い例外処理マクロをサポートしています。 MFC マクロと C++ 例外を混在させる方法については、「[例外 : MFC マクロと C++ 例外の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)」を参照してください。

[/EH](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを使用して、C++ プロジェクトで使用する例外処理モデルを指定します。 標準 C++ 例外処理 (**/EHsc**) は、Visual Studio の新しい C++ プロジェクトの既定です。

例外処理メカニズムを混在させることはお勧めしません。 たとえば、構造化例外処理では C++ 例外を使用しないでください。 C++ 例外処理を排他的に使用すると、コードの移植性が向上し、任意の型の例外を処理できます。 構造化例外処理の欠点の詳細については、「[構造化例外](structured-exception-handling-c-cpp.md)処理 」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

- [例外とエラー処理に関する最新の C++ のベスト プラクティス](errors-and-exception-handling-modern-cpp.md)

- [例外の安全性を設計する方法](how-to-design-for-exception-safety.md)

- [例外的なコードと非例外的なコードをインターフェイスで連結する方法](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [try、catch、および throw ステートメント](try-throw-and-catch-statements-cpp.md)

- [キャッチ ブロックの評価方法](how-catch-blocks-are-evaluated-cpp.md)

- [例外とスタックアンワインド](exceptions-and-stack-unwinding-in-cpp.md)

- [例外仕様](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [未処理の C++ 例外](unhandled-cpp-exceptions.md)

- [C (構造化) と C++ の混合例外](mixing-c-structured-and-cpp-exceptions.md)

- [構造化例外処理 (SEH) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](cpp-language-reference.md)</br>
[x64 の例外処理](../build/exception-handling-x64.md)</br>
[例外処理 (C++/CLI および C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
