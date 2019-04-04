---
title: メッセージ パッシング関数
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 1a1790a08403bcc1d016a39e27c7a121c288af4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303951"
---
# <a name="message-passing-functions"></a>メッセージ パッシング関数

Asynchronous Agents Library では、コンポーネント間でメッセージを渡すことができます関数がいくつか提供します。

これらのメッセージ パッシング関数は、さまざまなメッセージ ブロックの型で使用されます。 同時実行ランタイムによって定義されているメッセージ ブロックの型の詳細については、[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)を参照してください。

##  <a name="top"></a> セクション

このトピックでは、次のメッセージ パッシング関数について説明します。

- [送信および asend](#send)

- [受信および try_receive](#receive)

- [例](#examples)

##  <a name="send"></a> 送信および asend

[Concurrency::send](reference/concurrency-namespace-functions.md#send)関数のメッセージから指定したターゲットの同期的に送信し、 [concurrency::asend](reference/concurrency-namespace-functions.md#asend)関数のメッセージから指定された対象への非同期的に送信します。 両方の`send`と`asend`関数が、ターゲットが、これは最終的に同意または拒否メッセージを示すまでに待機します。

`send`関数が、ターゲットを受け入れるかを返す前に、メッセージを拒否するまでに待機します。 `send`関数が返される**true**場合は、メッセージの配信と**false**それ以外の場合。 `send`関数は同期的に、動作、`send`関数を返す前にメッセージを受信するターゲットを待機します。

逆に、`asend`関数が返す前に、メッセージを承諾または拒否するようにターゲットの待機しません。 代わりに、`asend`関数が返される**true**場合は、ターゲットがメッセージを受け入れるし、実行は最終的にします。 それ以外の場合、`asend`返します**false**を示すこと、ターゲットがメッセージを拒否または、メッセージを受け取るかどうかの決定を延期します。

[[トップ](#top)]

##  <a name="receive"></a> 受信および try_receive

[Concurrency::receive](reference/concurrency-namespace-functions.md#receive)と[concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive)関数は、指定したソースからデータを読み取ります。 `receive`関数は、使用可能になるデータを待機は、`try_receive`関数をすぐに返します。

使用して、`receive`続行データがある必要なときに機能します。 使用して、`try_receive`関数の場合は、現在のコンテキストをブロックする必要がありますまたは続行するデータが存在する必要はありません。

[[トップ](#top)]

##  <a name="examples"></a> 例

使用する例については、`send`と`asend`と`receive`関数の場合は、次のトピックを参照してください。

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [方法: さまざまなプロデューサー/コンシューマー パターンを実装する](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [方法: call クラスおよび transformer クラスに処理関数を提供する](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [方法: 完了したタスクから選択する](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [方法: メッセージを定期的に送信する](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [方法: メッセージ ブロック フィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[トップ](#top)]

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[send 関数](reference/concurrency-namespace-functions.md#send)<br/>
[asend 関数](reference/concurrency-namespace-functions.md#asend)<br/>
[receive 関数](reference/concurrency-namespace-functions.md#receive)<br/>
[try_receive 関数](reference/concurrency-namespace-functions.md#try_receive)
