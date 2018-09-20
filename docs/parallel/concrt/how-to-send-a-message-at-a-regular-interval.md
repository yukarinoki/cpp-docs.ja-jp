---
title: '方法: メッセージを定期的に送信する |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3c476d9cf633ce9b676dc8f658c94bd0b240461
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384299"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>方法: メッセージを定期的に送信する

この例は、同時実行性を使用する方法を示します::[timer クラス](../../parallel/concrt/reference/timer-class.md)を定期的にメッセージを送信します。

## <a name="example"></a>例

次の例では、`timer` オブジェクトを使用して、時間のかかる操作中に進行状況を報告します。 この例のリンク、`timer`オブジェクトを[concurrency::call](../../parallel/concrt/reference/call-class.md)オブジェクト。 `call` オブジェクトは、プログレス インジケーターをコンソールに定期的に出力します。 [::Start](reference/timer-class.md#start)メソッドは、別のコンテキストで、タイマーを実行します。 `perform_lengthy_operation`関数呼び出し、 [concurrency::wait](reference/concurrency-namespace-functions.md#wait)時間のかかる操作をシミュレートするために、メインのコンテキストで機能します。

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`report-progress.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc report-progress.cpp**

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)
