---
description: '詳細情報: メッセージパッシング関数'
title: メッセージ パッシング関数
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 77e221f5d2116c1bfc2690d247161979af04ac06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159857"
---
# <a name="message-passing-functions"></a>メッセージ パッシング関数

非同期エージェントライブラリには、コンポーネント間でメッセージを渡すための関数がいくつか用意されています。

これらのメッセージパッシング関数は、さまざまなメッセージブロックの型と共に使用されます。 同時実行ランタイムによって定義されるメッセージブロック型の詳細については、「 [非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="sections"></a><a name="top"></a> 各項

このトピックでは、次のメッセージパッシング関数について説明します。

- [send と asend](#send)

- [receive および try_receive](#receive)

- [使用例](#examples)

## <a name="send-and-asend"></a><a name="send"></a> send と asend

[Concurrency:: send](reference/concurrency-namespace-functions.md#send)関数は、指定されたターゲットにメッセージを同期的に送信します。 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend)関数は、指定されたターゲットにメッセージを非同期的に送信します。 関数と関数はどちらも、 `send` `asend` 最終的にメッセージを受け入れるか拒否することをターゲットが示すまで待機します。

関数は、が `send` 返される前に、ターゲットがメッセージを受け入れるか拒否するまで待機します。 この `send` 関数は、 **`true`** メッセージが配信された場合はを返し、それ以外の場合はを返し **`false`** ます。 関数は `send` 同期的に動作するため、 `send` 関数はを返す前に、ターゲットがメッセージを受信するまで待機します。

逆に、 `asend` この関数は、が返される前に、ターゲットがメッセージを受け入れたり拒否したりするのを待機しません。 代わりに、 `asend` **`true`** ターゲットがメッセージを受け入れ、最終的にそのメッセージを取得する場合、関数はを返します。 それ以外の場合、はを返して、 `asend` **`false`** ターゲットがメッセージを拒否したか、またはメッセージを取得するかどうかの決定を延期したことを示します。

[[上](#top)]

## <a name="receive-and-try_receive"></a><a name="receive"></a> receive および try_receive

[Concurrency:: receive](reference/concurrency-namespace-functions.md#receive)および[concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive)関数は、指定されたソースからデータを読み取ります。 関数は、 `receive` データが使用可能になるまで待機しますが、 `try_receive` 関数はすぐに制御を戻します。

続行するには、関数を使用し `receive` ます。 現在の `try_receive` コンテキストをブロックしない場合、またはデータを続行する必要がない場合は、関数を使用します。

[[上](#top)]

## <a name="examples"></a><a name="examples"></a> 使用例

関数、関数、および関数を使用する例については、 `send` `asend` 次のトピックを参照し `receive` てください。

- [非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [方法: さまざまな Producer-Consumer パターンを実装する](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [方法: call クラスおよびトランスフォーマークラスに処理関数を提供する](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [方法: データパイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [方法: 完了したタスクの中から選択する](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [方法: メッセージを定期的に送信する](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [方法: メッセージブロックフィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[上](#top)]

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[send 関数](reference/concurrency-namespace-functions.md#send)<br/>
[asend 関数](reference/concurrency-namespace-functions.md#asend)<br/>
[receive 関数](reference/concurrency-namespace-functions.md#receive)<br/>
[try_receive 関数](reference/concurrency-namespace-functions.md#try_receive)
