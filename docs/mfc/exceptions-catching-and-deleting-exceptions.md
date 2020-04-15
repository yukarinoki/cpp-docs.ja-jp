---
title: '例外処理 : 例外のキャッチと削除'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 74022c8bc6af1d2cdf74fa452d4e0483637e542e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365516"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>例外処理 : 例外のキャッチと削除

次の手順と例では、例外をキャッチして削除する方法を示します。 **try**キーワード **、catch**キーワード、および**スロー**キーワードの詳細については、「[例外とエラー処理に関する最新の C++ のベスト プラクティス](../cpp/errors-and-exception-handling-modern-cpp.md)」を参照してください。

例外を削除しないと、そのコードが例外をキャッチするたびにメモリ リークが発生するため、例外ハンドラーは、例外オブジェクトを削除する必要があります。

**catch**ブロックは、次の場合に例外を削除する必要があります。

- **catch**ブロックは新しい例外をスローします。

   もちろん、同じ例外を再度スローする場合は、例外を削除しないでください。

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- 実行は**catch**ブロック内から戻ります。

> [!NOTE]
> を削除する場合`CException`は、メンバー`Delete`関数を使用して例外を削除します。 例外がヒープ上にない場合は失敗する可能性があるため **、delete**キーワードは使用しないでください。

#### <a name="to-catch-and-delete-exceptions"></a>例外をキャッチして削除するには

1. **try**キーワードを使用して **、try**ブロックを設定します。 **try**ブロック内で例外をスローする可能性のあるプログラム ステートメントを実行します。

   **catch**キーワードを使用して **、catch**ブロックを設定します。 例外処理コードを**catch**ブロックに配置します。 **catch**ブロック内のコードが実行されるのは **、try**ブロック内のコードが**catch**ステートメントで指定された型の例外をスローした場合だけです。

   次のスケルトンは **、try**ブロックと**catch**ブロックが通常どのように配置されているかを示しています。

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   例外がスローされると、例外宣言が例外の型と一致する最初の**catch**ブロックに制御が渡されます。 次に示すように、連続した**catch**ブロックを使用して、さまざまな種類の例外を選択的に処理できます。

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

詳細については、「[例外 : MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
