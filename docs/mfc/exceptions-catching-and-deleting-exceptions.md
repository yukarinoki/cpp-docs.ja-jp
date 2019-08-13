---
title: 例外:キャッチと削除例外
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 511850c3c17a4eb70529202f4b0c2b36132fc8ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173294"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>例外:キャッチと削除例外

次の手順と例についてをキャッチし、例外を削除する方法を表示します。 詳細については、**try**、**catch**、および***throw**キーワードを参照してください[C++ 例外処理](../cpp/cpp-exception-handling.md)します。

そのコードが例外をキャッチするたびに、例外を削除する障害により、メモリ リークが発生しているため、例外ハンドラーは処理した例外オブジェクトを削除する必要があります。

**catch**ブロックが例外を削除する必要があるとき。

- **catch**ブロックが新しい例外をスローします。

   もちろん、もう一度同じ例外をスローする場合、例外を削除できません必要があります。

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- 内から実行が、**catch**ブロックします。

> [!NOTE]
>  削除するときに、`CException`を使用して、`Delete`例外を削除するメンバー関数。 使用しないでください、**delete**キーワード、ため、例外が、ヒープ上にない場合に失敗します。

#### <a name="to-catch-and-delete-exceptions"></a>キャッチし、例外を削除するには

1. **try**ブロックを設定するには、**try**キーワードを使用します。 **try**ブロック内で例外をスローする可能性のあるプログラムステートメントを実行します。

   **catch**キーワードを使用して、**catch**ブロックを設定します。 **catch**ブロックに例外処理コードを配置します。 **catch**ブロック内のコードは、**try**ブロック内のコードが**catch**ステートメントで指定されたタイプの例外をスローした場合にのみ実行されます。

   次のスケルトンは、**try**と**catch**ブロックの通常の配置方法を示しています。

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   最初に制御が移ります例外がスローされたときに**catch**ブロックの例外宣言、例外の種類に対応します。 シーケンシャルでの例外の種類を選択的に処理できる**catch**次に示すようにブロックします。

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

詳細については、次を参照してください。[例外。MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
