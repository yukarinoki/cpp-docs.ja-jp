---
description: '詳細については、「方法: メッセージを定期的に送信する」を参照してください。'
title: '方法: メッセージを定期的に送信する'
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: f65226d8101ddbadaee97a16f63512b9c8dcb41e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197285"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>方法: メッセージを定期的に送信する

この例では、concurrency::[timer クラス](../../parallel/concrt/reference/timer-class.md) を使用して、一定の間隔でメッセージを送信する方法を示します。

## <a name="example"></a>例

次の例では、`timer` オブジェクトを使用して、時間のかかる操作中に進行状況を報告します。 この例では、 `timer` オブジェクトを [concurrency:: call](../../parallel/concrt/reference/call-class.md) オブジェクトにリンクします。 `call` オブジェクトは、プログレス インジケーターをコンソールに定期的に出力します。 [Concurrency:: timer:: start](reference/timer-class.md#start)メソッドは、タイマーを別のコンテキストで実行します。 関数は、 `perform_lengthy_operation` メインコンテキストで [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 関数を呼び出して、時間のかかる操作をシミュレートします。

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `report-progress.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc report-progress**

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)
