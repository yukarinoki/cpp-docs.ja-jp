---
title: 例外:MFC マクロと C++ 例外を使用します。
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
ms.openlocfilehash: 00e88ddabf3a8e8b591bebae7ebc8ced0e1dc637
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406016"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>例外:MFC マクロと C++ 例外を使用します。

この記事では、MFC の例外処理マクロと C++ 例外処理のキーワードの両方を使用するコードの記述に関する考慮事項について説明します。

ここでは、次のトピックについて説明します。

- [例外のキーワードとマクロの混在](#_core_mixing_exception_keywords_and_macros)

- [Try catch ブロック内でのブロック](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> 例外のキーワードとマクロの混在

MFC 例外マクロと同じプログラム内での C++ 例外のキーワードを混在させることができます。 ただし、マクロは、例外オブジェクトを自動的に削除、有効範囲外に出ると、例外処理キーワードを使用して、コードは実行されませんので、同じブロック内の C++ 例外のキーワードを持つ MFC マクロを混ぜることはできません。 詳細については、この記事を参照してください。[例外。キャッチと削除例外](../mfc/exceptions-catching-and-deleting-exceptions.md)します。

マクロとキーワードの主な違いでは、例外がスコープ外になる、マクロがそのキャッチされた例外を「自動的に」削除することです。 キーワードを使用してコードを削除しません。catch ブロックでキャッチされた例外を明示的に削除する必要があります。 マクロと C++ 例外のキーワードまたは、メモリ リークが発生する例外オブジェクトを削除できなかった場合、ヒープの破損、例外が 2 回削除されるとします。

次のコードでは、例外ポインターなどが無効になります。

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

実行が「内部」の **CATCH** ブロックから出ると、 `e`が削除されるため、問題が発生します。 **THROW** ステートメントの代わりに **THROW_LAST** マクロを使用すると、「外部」の **CATCH** ブロックが有効なポインタを受け取るようになります。

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try Catch ブロック内でのブロック

**CATCH** ブロック内の **try** ブロック内から現在の例外を再スローすることはできません。 次の例は無効です。

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

詳細については、次を参照してください。[例外。例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
