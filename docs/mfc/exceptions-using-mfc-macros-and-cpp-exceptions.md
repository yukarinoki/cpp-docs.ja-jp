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
ms.openlocfilehash: d669c58da04a1cd0ead424d93f6fad6adcd4c56c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622737"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>例外処理 : MFC マクロと C++ 例外機構の使用

この記事では、MFC 例外処理マクロと C++ 例外処理キーワードの両方を使用するコードの記述に関する考慮事項について説明します。

この記事では、次のトピックについて説明します。

- [例外キーワードとマクロの混在](#_core_mixing_exception_keywords_and_macros)

- [Catch ブロック内の try ブロック](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>例外キーワードとマクロの混在

MFC 例外マクロと C++ 例外キーワードは、同じプログラムに混在させることができます。 ただし、MFC マクロと C++ 例外キーワードを混在させることはできません。これは、マクロがスコープ外に出ると例外オブジェクトを自動的に削除するのに対し、例外処理のキーワードを使用するコードには含まれていないためです。 詳細については、例外の[キャッチと削除](exceptions-catching-and-deleting-exceptions.md)に関する記事を参照してください。

マクロとキーワードの主な相違点は、例外がスコープ外に出ると、マクロがキャッチされた例外を自動的に削除することです。 キーワードを使用するコードでは、catch ブロックでキャッチされた例外は、明示的に削除する必要があります。 マクロと C++ 例外キーワードを混在させると、例外オブジェクトが削除されない場合、または例外が2回削除されたときにヒープが破損した場合に、メモリリークが発生する可能性があります。

たとえば、次のコードは例外ポインターを無効にします。

[!code-cpp[NVC_MFCExceptions#10](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

この問題が発生するの `e` は、"内部" **CATCH**ブロックから実行が渡されたときにが削除されるためです。 **THROW**ステートメントの代わりに**THROW_LAST**マクロを使用すると、"outer" **CATCH**ブロックが有効なポインターを受け取るようになります。

[!code-cpp[NVC_MFCExceptions#11](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>Catch ブロック内の try ブロック

**CATCH**ブロック内の**try**ブロック内から現在の例外を再スローすることはできません。 次の例は無効です。

[!code-cpp[NVC_MFCExceptions#12](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

詳細については、「例外[: 例外の内容の調査](exceptions-examining-exception-contents.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
