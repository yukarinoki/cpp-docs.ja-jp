---
title: '例外処理: MFC マクロと C++ 例外の使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c50e7358d29e04c81a5e443d5b1a03881fed7f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346062"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>例外処理 : MFC マクロと C++ 例外機構の使用
この記事では、MFC 例外処理マクロと C++ 例外処理のキーワードの両方を使用するコードを記述するための考慮事項について説明します。  
  
 ここでは、次のトピックについて説明します。  
  
-   [例外のキーワードとマクロの混在](#_core_mixing_exception_keywords_and_macros)  
  
-   [Try catch ブロック内のブロック](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> 例外のキーワードとマクロの混在  
 MFC 例外マクロと同じプログラムで C++ 例外処理キーワードを混在させることができます。 マクロ例外オブジェクトを自動的に削除のスコープ外に出ると、例外処理キーワードを使用するコードは実行されませんので、同じブロックでの C++ 例外のキーワードと MFC マクロを組み合わせることはできません。 詳細については、記事を参照してください。[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
 マクロとキーワードの主な違いは、例外がスコープ外に出るときに、マクロがそのキャッチした例外を「自動」削除することです。 キーワードを使用してコードを削除しません。catch ブロックでキャッチされた例外は、明示的に削除する必要があります。 マクロと C++ 例外処理キーワードまたは、メモリ リークが発生する例外オブジェクトを削除できなかった場合、例外が 2 回削除されたときにヒープが破損します。  
  
 次のコードには、たとえば、例外ポインターが無効になります。  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 問題は、`e`実行は、「内部」外から渡すときに削除**キャッチ**ブロックします。 使用して、`THROW_LAST`マクロの代わりに、**スロー**ステートメントが発生、「外部」**キャッチ**有効なポインターを受け取るブロック。  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try Catch ブロック内のブロック  
 内から現在の例外を再スローすることはできません、**再試行**ブロック内にある、**キャッチ**ブロックします。 次の例では、有効です。  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 詳細については、次を参照してください。[例外: 例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

