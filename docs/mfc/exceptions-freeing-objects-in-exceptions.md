---
title: '例外処理: 例外オブジェクトの解放 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21a63a55103cbefda2ba501c5609b772b2203166
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347829"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>例外処理 : 例外処理でのオブジェクトの解放
この記事では、必要と例外が発生したときに、オブジェクトを解放する方法について説明します。 ここでは、次の内容について説明します。  
  
-   [ローカルでの例外を処理します。](#_core_handling_the_exception_locally)  
  
-   [オブジェクトの破棄後に例外のスロー](#_core_throwing_exceptions_after_destroying_objects)  
  
 または、アプリケーションの割り込みの通常のプログラム フローによって、フレームワークによってスローされた例外。 したがって、ようにオブジェクトを追跡管理することが適切に破棄それらの例外がスローされた場合に非常に重要なことができます。  
  
 これを行う 2 つの主な方法があります。  
  
-   使用してローカル例外処理、**を再試行してください**と**キャッチ**キーワードは、1 つのステートメントのすべてのオブジェクトを破棄します。  
  
-   内の任意のオブジェクトを破棄、**キャッチ**さらに処理するため、ブロックの外側の例外をスローする前にブロックします。  
  
 これら 2 つの方法は、解決策を次の問題のある例として次に示します。  
  
 [!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]  
  
 上、書き込まれるにつれて`myPerson`によって例外がスローされた場合は削除されません`SomeFunc`です。 実行は、通常の関数の終了とオブジェクトを削除するコードをバイパスして、[次へ] の外側の例外ハンドラーに直接ジャンプします。 オブジェクトへのポインター スコープから外れたときにする場合、例外、関数、プログラムが実行されている限り、オブジェクトが占有するメモリは解放されません。 これは、メモリ リークが発生します。メモリ診断を使用して検出します。  
  
##  <a name="_core_handling_the_exception_locally"></a> ローカルでの例外を処理します。  
 **Try ブロックと catch**パラダイムがメモリ リークを回避し、例外が発生したときに、オブジェクトが破棄されることを確保するための防御プログラミング メソッドを提供します。 たとえば、この記事の前半に示した例書き換えるとおり。  
  
 [!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]  
  
 この新しい例は、例外をキャッチし、それをローカルで処理する例外ハンドラーを設定します。 関数を正常に終了し、オブジェクトを破棄します。 この例の重要な側面で例外をキャッチするときにコンテキストが確立されている、 **try ブロックと catch**ブロックします。 ローカル例外フレームせず、関数はわかりません例外がスローされた、正常終了して、オブジェクトを破棄する機会はありません。  
  
##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> オブジェクトの破棄後に例外のスロー  
 例外を処理する別の方法では、[次へ] の外側の例外処理コンテキストに渡します。 **キャッチ**ブロックで、ローカルで割り当てられたオブジェクトの一部のクリーンアップを実行でき、さらに処理するため、例外をスローします。  
  
 スロー元の関数は可能性があります。 またはヒープ オブジェクトの割り当てを解除する必要はありません。 場合、関数が、通常のケースを返す前に常に、ヒープのオブジェクトの割り当てを解除し、関数は、必要がありますも割り当てを解除ヒープ オブジェクト、例外をスローする前にします。 その一方で、関数では、オブジェクトは通常は、通常のケースを返す前に解放されない場合する必要がありますで個別にヒープ オブジェクトの割り当てを解除するかどうか。  
  
 オブジェクトに、ローカルに割り当てられていれば、次の例に示すをクリーンアップできます。  
  
 [!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]  
  
 例外処理機構に自動的に割り当て解除フレーム オブジェクトです。フレーム オブジェクトのデストラクターが呼び出されます。  
  
 例外をスローする関数を呼び出す場合を使用できます**try ブロックと catch**ブロックが例外をキャッチし、作成した任意のオブジェクトを破棄する機会があるかどうかを確認します。 具体的には、MFC 関数の多くが例外をスローできることに注意してください。  
  
 詳細については、次を参照してください。[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

