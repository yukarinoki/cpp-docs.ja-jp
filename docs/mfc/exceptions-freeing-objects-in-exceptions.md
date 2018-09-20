---
title: '例外処理: 例外オブジェクトの解放 |Microsoft Docs'
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
ms.openlocfilehash: f0f7c9c28e438ad9d5cf643f005175512192be80
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390769"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>例外処理 : 例外処理でのオブジェクトの解放

この記事では、必要性と例外が発生したときに、オブジェクトを解放する方法について説明します。 ここでは、次の内容について説明します。

- [ローカルでの例外を処理します。](#_core_handling_the_exception_locally)

- [オブジェクトの破棄後に例外のスロー](#_core_throwing_exceptions_after_destroying_objects)

または、アプリケーションの割り込みの通常のプログラム フローで、フレームワークによってスローされる例外。 そのため、例外がスローされた場合に適切に破棄することができますようにオブジェクトを追跡管理を維持する非常に重要ですが。

これを行う 2 つの主な方法があります。

- 使用してローカル例外処理、**お試しください**と**キャッチ**キーワードは、1 つのステートメントを使用してすべてのオブジェクトを破棄します。

- 内の任意のオブジェクトを破棄、**キャッチ**さらに処理するため、ブロックの外側の例外をスローする前にブロックします。

これら 2 つの方法は、問題のある例を次の解決策として次に示します。

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

上記のとおり`myPerson`によって例外がスローされた場合は削除されません`SomeFunc`します。 実行は、通常の関数が終了し、オブジェクトを削除するコードをバイパスして、[次へ] の外側の例外ハンドラーに直接ジャンプします。 オブジェクトへのポインターはスコープから外れる、例外が、関数を離れるし、プログラムが実行されている限り、オブジェクトに占有されたメモリは復旧されません。 これは、メモリ リークが発生します。これについては、メモリ診断を使用して検出します。

##  <a name="_core_handling_the_exception_locally"></a> ローカルでの例外を処理します。

**Try ~ catch**パラダイムのメモリ リークを回避して、例外が発生したときに、オブジェクトが破棄されることを確保防御的なプログラミング方法を提供します。 たとえば、この記事の前半で示した例は次のように書き換えることができます。

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

この新しい例は、例外をキャッチし、それをローカルで処理するための例外ハンドラーを設定します。 関数が正常終了したし、オブジェクトを破棄します。 この例の重要な側面はで、例外をキャッチするコンテキストが確立されていること、 **try ~ catch**ブロック。 ローカル例外フレーム、せず、関数がわからなくなります例外がスローされ、通常どおりに終了して、オブジェクトを破棄することはありません。

##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> オブジェクトの破棄後に例外のスロー

例外を処理する別の方法では、[次へ] の外側の例外処理コンテキストに渡すことです。 **キャッチ**ブロックをローカルで割り当てられたオブジェクトのクリーンアップ処理を実行でき、さらに処理するため例外をスローします。

スロー関数は可能性があります。 またはヒープのオブジェクトの割り当てを解除する必要はありません。 場合は、関数が、通常の場合に返す前に常にヒープのオブジェクトの割り当てを解除し、関数は、する必要がありますも割り当てを解除ヒープ オブジェクト、例外をスローする前に。 その一方で、関数では、オブジェクトは通常は、通常の場合に返す前に解放されない場合する必要がありますで個別にヒープのオブジェクトの割り当てを解除するかどうか。

次の例はローカルでどのように割り当てられているオブジェクトをクリーンアップできます。

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

例外処理機構フレーム オブジェクトを自動的に割り当て解除します。フレーム オブジェクトのデストラクターが呼び出されます。

例外をスローする関数を呼び出す場合は使用できます**try ~ catch**ブロックを必ず、例外をキャッチして、作成した任意のオブジェクトを破棄する可能性があります。 具体的には、MFC 関数の多くが例外をスローすることもあります。

詳細については、次を参照してください。[例外。 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

