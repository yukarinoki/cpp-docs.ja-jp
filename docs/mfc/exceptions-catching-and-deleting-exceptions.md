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
ms.openlocfilehash: 370062d3e17127e711f2b4356cbb133a6c1d20b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625910"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>例外処理 : 例外のキャッチと削除

次の手順と例についてをキャッチし、例外を削除する方法を表示します。 詳細については、**お試しください**、**キャッチ**、および**スロー**キーワードを参照してください[C++ 例外処理](../cpp/cpp-exception-handling.md)します。

そのコードが例外をキャッチするたびに、例外を削除する障害により、メモリ リークが発生しているため、例外ハンドラーは処理した例外オブジェクトを削除する必要があります。

**キャッチ**ブロックが例外を削除する必要があるとき。

- **キャッチ**ブロックが新しい例外をスローします。

   もちろん、もう一度同じ例外をスローする場合、例外を削除できません必要があります。

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- 内から実行が、**キャッチ**ブロックします。

> [!NOTE]
>  削除するときに、`CException`を使用して、`Delete`例外を削除するメンバー関数。 使用しないでください、**削除**キーワード、ため、例外が、ヒープ上にない場合に失敗します。

#### <a name="to-catch-and-delete-exceptions"></a>キャッチし、例外を削除するには

1. 使用して、**お試しください**を設定するキーワード、**お試しください**ブロック。 内で例外をスローするすべてのプログラム ステートメントを実行する**お試しください**ブロックします。

   使用して、**キャッチ**を設定するキーワード、**キャッチ**ブロック。 例外処理コードを**キャッチ**ブロックします。 コードでは、**キャッチ**場合にのみブロックが実行内のコード、**お試しください**ブロックで指定された型の例外をスローする、**キャッチ**ステートメント。

   次のスケルトンに示す方法**を再試行してください**と**キャッチ**ブロックは正常に配置されます。

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   最初に制御が移ります例外がスローされたときに**キャッチ**ブロックの例外宣言、例外の種類に対応します。 シーケンシャルでの例外の種類を選択的に処理できる**キャッチ**次に示すようにブロックします。

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

詳細については、次を参照してください。[例外: MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

