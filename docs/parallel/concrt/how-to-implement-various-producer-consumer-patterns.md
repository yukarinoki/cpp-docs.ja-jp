---
title: '方法: さまざまなプロデューサー/コンシューマー パターンを実装する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50a6683db37fb6e994c1957a8df3ab6469acff6d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>方法: さまざまなプロデューサー/コンシューマー パターンを実装する
ここでは、アプリケーションにプロデューサー/コンシューマー パターンを実装する方法について説明します。 このパターンでは、"*プロデューサー*" がメッセージをメッセージ ブロックに送信し、"*コンシューマー*" がそのブロックからメッセージを読み取ります。  
  
 このトピックでは、2 つのシナリオに従って説明します。 最初のシナリオでは、コンシューマーはプロデューサーが送信した各メッセージを受信する必要があります。 2 番目のシナリオでは、コンシューマーは定期的にデータをポーリングします。そのため、各メッセージを受信する必要はありません。  
  
 このトピックのどちらの例も、エージェント、メッセージ ブロック、およびメッセージ パッシング関数を使用して、メッセージをプロデューサーからコンシューマーに転送します。 プロデューサー エージェントを使用して、 [concurrency::send](reference/concurrency-namespace-functions.md#send)にメッセージを書き込むための関数、 [concurrency::itarget](../../parallel/concrt/reference/itarget-class.md)オブジェクト。 コンシューマー エージェントを使用して、 [concurrency::receive](reference/concurrency-namespace-functions.md#receive)からのメッセージを読み取る関数を[concurrency::isource](../../parallel/concrt/reference/isource-class.md)オブジェクト。 どちらのエージェントにも、処理の終了を調整するための sentinel 値が保持されます。  
  
 非同期エージェントの詳細については、次を参照してください。[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)です。 メッセージ ブロックとメッセージ パッシング関数の詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)と[メッセージを渡す関数](../../parallel/concrt/message-passing-functions.md)です。  
  
## <a name="example"></a>例  
 この例では、プロデューサー エージェントは一連の数字をコンシューマー エージェントに送信します。 コンシューマーはこれらの各数字を受け取り、その平均を計算します。 アプリケーションはその平均をコンソールに出力します。  
  
 この例では、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)キュー メッセージをプロデューサーを有効にするオブジェクト。 `unbounded_buffer` クラスに、`ITarget` および `ISource` を実装して、プロデューサーおよびコンシューマーと共有バッファーとの間でメッセージを送受信できるようにします。 `send` 関数および `receive` 関数で、プロデューサーからコンシューマーにデータを伝達するタスクを調整します。  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
The average is 50.  
```  
  
## <a name="example"></a>例  
 この例では、プロデューサー エージェントは一連の株式相場をコンシューマー エージェントに送信します。 コンシューマー エージェントは定期的に現在の相場を読み取り、それをコンソールに出力します。  
  
 この例に似ていますが、以前を使用する点を除いて、 [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)プロデューサーがコンシューマーと 1 つのメッセージを共有するを有効にするオブジェクト。 前の例と同様に、`overwrite_buffer` クラスに、`ITarget` および `ISource` を実装して、プロデューサーおよびコンシューマーが共有メッセージ バッファーを操作できるようにします。  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
Current quote is 24.44.  
Current quote is 24.44.  
Current quote is 24.65.  
Current quote is 24.99.  
Current quote is 23.76.  
Current quote is 22.30.  
Current quote is 25.89.  
```  
  
 `unbounded_buffer` オブジェクトとは異なり、`receive` 関数によって、`overwrite_buffer` オブジェクトからメッセージが削除されることはありません。 プロデューサーがメッセージを上書きする前に、コンシューマーがメッセージ バッファーから 2 回以上読み取りを行った場合、コンシューマーは毎回同じメッセージを取得します。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`producer-consumer.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc producer-consumer.cpp**  
  
## <a name="see-also"></a>関連項目  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)
