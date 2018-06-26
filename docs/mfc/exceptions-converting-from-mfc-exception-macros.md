---
title: '例外処理: MFC 例外マクロからの変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a386de558730e12bb8cf40da250c1d04dd4ff37a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931119"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>例外処理 : 古いコードの変換
これは、高度なトピックです。  
  
 この記事は、Microsoft Foundation Class マクロで記述された既存のコードに変換する方法を説明します:**を再試行してください**、**キャッチ**、**スロー**など — C++ 例外処理を使用するにはキーワード**再試行**、**キャッチ**と**スロー**です。 ここでは、次の内容について説明します。  
  
-   [変換の利点があります。](#_core_advantages_of_converting)  
  
-   [例外処理マクロ C++ の例外を使用するとコードの変換](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> 変換する利点  
 可能性があります必要はありません、既存のコードを変換するが、mfc バージョン 3.0 マクロの実装と以前のバージョンでの実装の違いに注意してください。 これらの相違点とコードの動作で行われる変更については[例外: Version 3.0 での例外処理マクロを変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)です。  
  
 変換する主要な利点は次のとおりです。  
  
-   C++ 例外処理のキーワードを使用するコードは、わずかに小さいをコンパイルします。EXE またはします。DLL です。  
  
-   C++ 例外処理キーワードは、柔軟性の高い: コピーできる任意のデータ型の例外を処理できる (**int**、 **float**、 **char**など) であるのに対し、マクロの例外を処理する`CException`し、そこから派生したクラスです。  
  
 マクロとキーワードの大きな違いは、例外がスコープ外に出るときに、「自動的に」マクロを使用してコードが例外をキャッチしましたによって削除されます。 コードを使用して、キーワードがないため、キャッチした例外を明示的に削除する必要があります。 詳細については、記事を参照してください。[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
 別の相違点は、構文です。 マクロとキーワードの構文は、次の 3 つの点で異なります。  
  
1.  マクロの引数と例外の宣言  
  
     A**キャッチ**マクロの呼び出しは、次の構文。  
  
     **キャッチ (** *exception_class*、*ことは* **)**  
  
     クラス名とオブジェクト ポインター名のコンマのことを確認します。  
  
     例外宣言、**キャッチ**キーワードはこの構文を使用します。  
  
     **キャッチ (** *exception_type* *exception_name * * *)**  
  
     このステートメントは catch の例外の種類を示すブロックで処理します。  
  
2.  Catch ブロックの区切り:  
  
     マクロで、**キャッチ**(とその引数) のマクロが最初の catch ブロックを開始以外の場合は、 **AND_CATCH**マクロは、後続の catch ブロックを開始し、 **END_CATCH**マクロcatch ブロックのシーケンスを終了します。  
  
     キーワードと、**キャッチ**(例外宣言) のキーワードは、各 catch ブロックを開始します。 相当するはありません、 **END_CATCH**マクロ; catch の最後に、終わりかっこをブロックします。  
  
3.  Throw 式:  
  
     マクロを使用して**THROW_LAST**を現在の例外を再スローします。 **スロー**キーワードを引数なしで同じ効果があります。  
  
##  <a name="_core_doing_the_conversion"></a> 変換を行う  
  
#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>C++ 例外処理キーワードを使用するマクロを使用してコードを変換するには  
  
1.  MFC のマクロの発生箇所をすべて検索**再試行**、**キャッチ**、 **AND_CATCH**、 **END_CATCH**、**スロー**、および**THROW_LAST**です。  
  
2.  置換またはマクロを次のすべての出現を削除します。  
  
     **再試行**(コードに置き換えます**再試行**)  
  
     **キャッチ**(コードに置き換えます**キャッチ**)  
  
     **AND_CATCH** (コードに置き換えます**キャッチ**)  
  
     **END_CATCH** (削除)  
  
     **スロー** (コードに置き換えます**スロー**)  
  
     **THROW_LAST** (コードに置き換えます**スロー**)  
  
3.  有効な例外宣言が形成されるように、マクロの引数を変更します。  
  
     たとえば、変更します。  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     から  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  Catch ブロック内のコードは、必要に応じて例外オブジェクトが削除されるように変更します。 詳細については、記事を参照してください。[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
 MFC 例外マクロを使用して例外処理コードの例を次に示します。 次の例のコードは、マクロ、例外を使用しているために注意してください`e`は自動的に削除します。  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 次の例のコードでは、例外を明示的に削除する必要がありますので C++ 例外のキーワードを使用します。  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 詳細については、次を参照してください。[例外: MFC マクロと C++ 例外](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

