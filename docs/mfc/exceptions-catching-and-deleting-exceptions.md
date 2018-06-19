---
title: '例外処理: 例外のキャッチと例外の削除 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3527dabab96fe8f2832430f928a922941178ea97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345187"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>例外処理 : 例外のキャッチと削除
次の手順と例についてをキャッチして例外を削除する方法を示します。 詳細については、**再試行**、**キャッチ**と`throw`キーワードを参照してください[C++ 例外処理](../cpp/cpp-exception-handling.md)です。  
  
 例外ハンドラーは、そのコードが例外をキャッチするたびに、例外の削除に失敗が、メモリ リークを引き起こします処理した例外オブジェクトを削除する必要があります。  
  
 **キャッチ**ブロックが例外を削除する必要があるとき。  
  
-   **キャッチ**ブロックは、新しい例外をスローします。  
  
     もちろん、もう一度同じ例外をスローする場合は、例外を削除する必要があります。  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   内から実行を返します、**キャッチ**ブロックします。  
  
> [!NOTE]
>  削除するときに、`CException`を使用して、**削除**例外を削除するメンバー関数。 使用しないでください、**削除**キーワードでは失敗する場合、この例外は、ヒープ上にないためです。  
  
#### <a name="to-catch-and-delete-exceptions"></a>キャッチおよび例外を削除するには  
  
1.  使用して、**を再試行してください**キーワードを設定する、**再試行**ブロックします。 内で例外をスローするすべてのプログラム ステートメントの実行、**再試行**ブロックします。  
  
     使用して、**キャッチ**を設定するキーワード、**キャッチ**ブロックします。 例外処理コード、**キャッチ**ブロックします。 内のコード、**キャッチ**ブロックが実行される場合にのみ内のコード、**を再試行してください**ブロックで指定された型の例外をスローする、**キャッチ**ステートメントです。  
  
     次のスケルトンの表示方法**を再試行してください**と**キャッチ**ブロックを通常配置。  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     最初に制御が渡される例外がスローされると、**キャッチ**ブロックの例外宣言は、例外の種類に対応します。 シーケンシャルでの例外の種類を選択的に処理できる**キャッチ**次に示すようにブロックします。  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 詳細については、次を参照してください。[例外: MFC 例外マクロからの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

