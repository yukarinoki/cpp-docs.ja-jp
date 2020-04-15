---
title: '例外処理 : MFC マクロと C++ 例外機構の使用'
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: afad5335bedf001329ecb401a8a16c663afb5571
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371591"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>例外処理 : MFC マクロと C++ 例外機構の使用

この資料では、MFC 例外処理マクロと C++ 例外処理キーワードの両方を使用するコードを記述する場合の考慮事項について説明します。

この記事では、次のトピックについて説明します。

- [例外キーワードとマクロの混在](#_core_mixing_exception_keywords_and_macros)

- [キャッチブロック内のブロックを試す](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>例外キーワードとマクロの混在

MFC 例外マクロと C++ 例外キーワードを同じプログラムに混在させることができます。 ただし、MFC マクロと C++ 例外キーワードを同じブロックに混在させることはできません。 詳細については、「例外 :[例外のキャッチと削除 」を参照してください](../mfc/exceptions-catching-and-deleting-exceptions.md)。

マクロとキーワードの主な違いは、例外がスコープ外になったときに、マクロがキャッチされた例外を 「自動的に」 削除することです。 キーワードを使用するコードは、使用しません。catch ブロックでキャッチされた例外は明示的に削除する必要があります。 マクロと C++ 例外キーワードを混在させると、例外オブジェクトが削除されないとメモリ リークが発生したり、例外が 2 回削除された場合にヒープが破損したりする可能性があります。

たとえば、次のコードは例外ポインターを無効にします。

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

この問題は、実行`e`が "内部" **CATCH**ブロックから抜け出すと削除されるために発生します。 **THROW**ステートメントの代わりに**THROW_LAST**マクロを使用すると、"外部" **CATCH**ブロックが有効なポインターを受け取ります。

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>キャッチブロック内のブロックを試す

**CATCH**ブロック内にある**try**ブロック内から現在の例外を再スローすることはできません。 次の例は無効です。

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

詳細については、「[例外 : 例外の内容の確認](../mfc/exceptions-examining-exception-contents.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
