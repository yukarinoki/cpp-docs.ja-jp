---
title: '例外処理 : 例外処理でのオブジェクトの解放'
ms.date: 11/04/2016
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
ms.openlocfilehash: 49c7c6b0481f90baa23609c1bb1596deda49f7bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371998"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>例外処理 : 例外処理でのオブジェクトの解放

この資料では、例外が発生したときにオブジェクトを解放する必要性と方法について説明します。 取り上げるトピックは次のとおりです。

- [例外をローカルで処理する](#_core_handling_the_exception_locally)

- [オブジェクトを破棄した後に例外をスローする](#_core_throwing_exceptions_after_destroying_objects)

フレームワークまたはアプリケーションによってスローされる例外は、通常のプログラム フローを中断します。 したがって、例外がスローされた場合に適切に破棄できるように、オブジェクトを厳密に追跡しておくことが非常に重要です。

これには、2 つの主な方法があります。

- **try**キーワードと**catch**キーワードを使用して例外をローカルで処理し、1 つのステートメントですべてのオブジェクトを破棄します。

- キャッチ**ブロック内**のオブジェクトを破棄してから、例外をブロックの外部にスローして処理を続行します。

以下に、問題のある例の解決策として、これら 2 つのアプローチを示します。

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

上記のように、`myPerson`例外が によって`SomeFunc`スローされた場合は削除されません。 実行は、次の外部例外ハンドラに直接ジャンプし、通常の関数の終了とオブジェクトを削除するコードをバイパスします。 例外が関数から抜け出すとオブジェクトへのポインターがスコープ外になり、プログラムが実行されている限りオブジェクトが占有するメモリは回復されません。 これはメモリ リークです。メモリ診断を使用して検出されます。

## <a name="handling-the-exception-locally"></a><a name="_core_handling_the_exception_locally"></a>例外をローカルで処理する

**try/catch**パラダイムは、メモリ リークを回避し、例外が発生したときにオブジェクトが破棄されるようにするための、防御的なプログラミング方法を提供します。 たとえば、この資料の前半で示した例は、次のように書き直します。

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

この新しい例では、例外をキャッチしてローカルで処理する例外ハンドラーを設定します。 次に、関数を正常に終了し、オブジェクトを破棄します。 この例の重要な側面は、例外をキャッチするコンテキストが**try/catch**ブロックで確立されるということです。 ローカル例外フレームがないと、例外がスローされたことは決してわかりませんし、正常に終了してオブジェクトを破棄する機会がありません。

## <a name="throwing-exceptions-after-destroying-objects"></a><a name="_core_throwing_exceptions_after_destroying_objects"></a>オブジェクトを破棄した後に例外をスローする

例外を処理するもう 1 つの方法は、次の外部例外処理コンテキストに渡す方法です。 **catch**ブロックでは、ローカルに割り当てられたオブジェクトのクリーンアップを実行し、例外をスローして処理を続行できます。

スローする関数は、ヒープ オブジェクトの割り当てを解除する必要がある場合と必要ない場合があります。 関数が通常のケースで返される前に常にヒープ オブジェクトの割り当てを解除する場合、関数は例外をスローする前にヒープ オブジェクトの割り当てを解除する必要があります。 一方、関数が通常の場合に戻る前にオブジェクトの割り当てを解除しない場合は、ヒープ オブジェクトの割り当てを解除するかどうかをケースバイケースで決定する必要があります。

次の例は、ローカルに割り当てられたオブジェクトをクリーンアップする方法を示しています。

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

例外メカニズムは、フレーム オブジェクトの割り当てを自動的に解除します。フレーム オブジェクトのデストラクターも呼び出されます。

例外をスローできる関数を呼び出す場合は **、try/catch**ブロックを使用して、例外をキャッチし、作成したオブジェクトを破棄する機会があることを確認できます。 特に、多くの MFC 関数が例外をスローする可能性があることに注意してください。

詳細については、「[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)
