---
title: メッセージ パッシング関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecb7d2a45079ff14740167a192eafaab268150
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688051"
---
# <a name="message-passing-functions"></a>メッセージ パッシング関数
非同期エージェント ライブラリは、コンポーネント間でメッセージを渡すことが許可される複数の機能を提供します。  
  
 これらのメッセージ パッシング関数は、さまざまなメッセージ ブロックの型で使用されます。 同時実行ランタイムによって定義されているメッセージ ブロックの型の詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
##  <a name="top"></a> セクション  
 このトピックでは、次のメッセージ パッシング関数について説明します。  
  
-   [送信および asend](#send)  
  
-   [受信および try_receive](#receive)  
  
-   [例](#examples)  
  
##  <a name="send"></a> 送信および asend  

 [Concurrency::send](reference/concurrency-namespace-functions.md#send)関数にメッセージを送信、指定したターゲット同期的に、 [concurrency::asend](reference/concurrency-namespace-functions.md#asend)関数のメッセージから、指定された対象への非同期的に送信します。 両方の`send`と`asend`関数を待ってターゲットするには最終的に同意または拒否メッセージを示します。  
  
 `send`関数は、ターゲットを受け入れるかを返す前に、メッセージを拒否するまで待機します。 `send`関数が返される`true`メッセージが配信されなかった場合と`false`それ以外の場合。 `send`関数は同期的に、動作、`send`関数を返す前にメッセージを受信するターゲットを待機します。  
  
 これに対し、`asend`関数は、ターゲットに同意するか、メッセージを返す前に待機しません。 代わりに、`asend`関数が返される`true`ターゲットがメッセージを受け入れるし、実行は最終的にします。 それ以外の場合、`asend`返します`false`を示すこと、ターゲットがメッセージを拒否されました。 または、メッセージを受け取るかどうかに関する決定を延期します。  
  
 [[トップ](#top)]  
  
##  <a name="receive"></a> 受信および try_receive  

 [Concurrency::receive](reference/concurrency-namespace-functions.md#receive)と[:try_receive](reference/concurrency-namespace-functions.md#try_receive)関数は、特定のソースからデータを読み取ります。 `receive`関数が、使用可能になるデータを待って一方、`try_receive`関数が直ちに返されます。  
  
 使用して、`receive`関数の場合、データを続行する必要があります。 使用して、`try_receive`関数の場合は、現在のコンテキストをブロックする必要がありますまたは続行するデータが存在する必要はありません。  
  
 [[トップ](#top)]  
  
##  <a name="examples"></a> 例  
 使用する例について、`send`と`asend`、および`receive`関数は、次のトピックを参照してください。  
  
-   [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [方法: さまざまなプロデューサー/コンシューマー パターンを実装する](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [方法: call クラスおよび transformer クラスに処理関数を提供する](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [方法: 完了したタスクから選択する](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [方法: メッセージを定期的に送信する](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [方法: メッセージ ブロック フィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 [[トップ](#top)]  
  
## <a name="see-also"></a>関連項目  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send 関数](reference/concurrency-namespace-functions.md#send)   
 [asend 関数](reference/concurrency-namespace-functions.md#asend)   
 [receive 関数](reference/concurrency-namespace-functions.md#receive)   
 [try_receive 関数](reference/concurrency-namespace-functions.md#try_receive)


