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
ms.openlocfilehash: a02b71609ec19d6106153bf67e9d56b860cfdfff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217936"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>例外処理 : 例外処理でのオブジェクトの解放

この記事では、例外が発生したときにオブジェクトを解放するためのニーズとメソッドについて説明します。 取り上げるトピックは次のとおりです。

- [例外をローカルで処理する](#_core_handling_the_exception_locally)

- [オブジェクトの破棄後に例外をスローする](#_core_throwing_exceptions_after_destroying_objects)

フレームワークまたはアプリケーションによってスローされる例外は、通常のプログラムフローに割り込みます。 したがって、例外がスローされた場合に適切に破棄できるように、オブジェクトを閉じておくことが非常に重要です。

これを行うには、2つの主要な方法があります。

- キーワードとキーワードを使用して例外をローカル **`try`** **`catch`** で処理し、1つのステートメントを使用してすべてのオブジェクトを破棄します。

- ブロックの **`catch`** 外部で例外をスローする前に、ブロック内のオブジェクトをすべて破棄します。

次の2つの方法は、次のような問題のある例の解決策として示されています。

[!code-cpp[NVC_MFCExceptions#14](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

上で記述したように、 `myPerson` によって例外がスローされた場合、は削除されません `SomeFunc` 。 実行は、通常の関数の終了およびオブジェクトを削除するコードをバイパスして、次の外側の例外ハンドラーに直接ジャンプします。 オブジェクトへのポインターは、例外が関数を終了したときにスコープ外になります。プログラムが実行されている限り、オブジェクトによって占有されているメモリは復旧されません。 これはメモリリークです。これは、メモリ診断を使用して検出されます。

## <a name="handling-the-exception-locally"></a><a name="_core_handling_the_exception_locally"></a>例外をローカルで処理する

**Try/catch**パラダイムは、メモリリークを回避し、例外が発生したときにオブジェクトが確実に破棄されるようにするための、防御的なプログラミング手法を提供します。 たとえば、この記事の前半で説明した例は、次のように書き換えることができます。

[!code-cpp[NVC_MFCExceptions#15](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

この新しい例では、例外ハンドラーを設定して例外をキャッチし、ローカルで処理します。 次に、関数が正常に終了し、オブジェクトが破棄されます。 この例の重要な側面は、例外をキャッチするコンテキストが try ブロックと**catch**ブロックを使用して確立されることです。 ローカル例外フレームがない場合、関数は、例外がスローされたことを認識しないため、正常に終了してオブジェクトを破棄する機会がありません。

## <a name="throwing-exceptions-after-destroying-objects"></a><a name="_core_throwing_exceptions_after_destroying_objects"></a>オブジェクトの破棄後に例外をスローする

例外を処理するもう1つの方法は、例外を次の外側の例外処理コンテキストに渡すことです。 ブロックでは **`catch`** 、ローカルに割り当てられたオブジェクトのクリーンアップを実行し、さらに処理するために例外をスローすることができます。

スローする関数は、ヒープオブジェクトの割り当てを解除する必要がある場合とない場合があります。 関数が通常のケースでを返す前にヒープオブジェクトの割り当てを解除する場合、関数は、例外をスローする前にヒープオブジェクトの割り当てを解除する必要があります。 一方、通常のケースでが返される前に関数がオブジェクトの割り当てを解除しない場合は、ヒープオブジェクトの割り当てを解除するかどうかをケースバイケースで決定する必要があります。

次の例は、ローカルに割り当てられたオブジェクトをクリーンアップする方法を示しています。

[!code-cpp[NVC_MFCExceptions#16](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

例外メカニズムは、フレームオブジェクトを自動的に解放します。フレームオブジェクトのデストラクターも呼び出されます。

例外をスローする可能性のある関数を呼び出す場合は、try ブロックと**catch**ブロックを使用して、例外をキャッチし、作成したオブジェクトを破棄する機会を確保することができます。 特に、多くの MFC 関数では例外がスローされる可能性があることに注意してください。

詳細については、「[例外: 例外のキャッチと削除](exceptions-catching-and-deleting-exceptions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
