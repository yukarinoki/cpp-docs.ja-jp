---
description: 詳細については、「メッセージの送信と受信」を参照してください。
title: メッセージの送信と受信
ms.date: 11/04/2016
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
ms.openlocfilehash: 3a61346c51ce035f6fd5a53b8c329ef81154b089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203212"
---
# <a name="message-sending-and-receiving"></a>メッセージの送信と受信

プロセスの送信部分と、フレームワークがどのように応答するかを検討します。

ほとんどのメッセージは、プログラムとのユーザー操作の結果として生成されます。 コマンドは、メニュー項目またはツールバーボタンのマウスクリック、またはアクセラレータのキー入力によって生成されます。 ユーザーは、ウィンドウの移動やサイズ変更など、Windows メッセージを生成することもできます。 その他の Windows メッセージは、プログラムの起動や終了などのイベントが発生したとき、windows がフォーカスを取得したり失ったりしたときに送信されます。 コントロール通知メッセージは、マウスクリックや、ダイアログボックスのボタンやリストボックスコントロールなどのコントロールを使用したその他のユーザー操作によって生成されます。

`Run`クラスのメンバー関数は、 `CWinApp` メッセージを取得し、適切なウィンドウにディスパッチします。 ほとんどのコマンドメッセージは、アプリケーションのメインフレームウィンドウに送信されます。 `WindowProc`クラスライブラリによって定義済みのはメッセージを取得し、受信したメッセージのカテゴリに応じて異なる方法でルーティングします。

次に、プロセスの受信部分を検討します。

メッセージの最初の受信者は、ウィンドウオブジェクトである必要があります。 Windows メッセージは通常、そのウィンドウオブジェクトによって直接処理されます。 コマンドメッセージは、通常、アプリケーションのメインフレームウィンドウで生成され、コマンド [ルーティング](command-routing.md)に記述されているコマンドターゲットチェーンにルーティングされます。

メッセージまたはコマンドを受け取ることができる各オブジェクトには、メッセージまたはコマンドとそのハンドラー名を組み合わせた独自のメッセージマップがあります。

コマンドターゲットオブジェクトがメッセージまたはコマンドを受け取ると、メッセージマップで一致が検索されます。 メッセージのハンドラーが見つかった場合は、ハンドラーを呼び出します。 メッセージマップの検索方法の詳細については、「 [フレームワークがメッセージマップを検索する方法](how-the-framework-searches-message-maps.md)」を参照してください。 フレームワークの図 [コマンド](user-interface-objects-and-command-ids.md)をもう一度参照してください。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)
