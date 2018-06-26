---
title: メッセージの送信と受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55f450085c446503ebf86960dbee1b0d930691c2
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932005"
---
# <a name="message-sending-and-receiving"></a>メッセージの送信と受信
プロセスおよびフレームワークの応答の送信側の一部を検討してください。  
  
 ほとんどのメッセージは、プログラムでのユーザー操作の結果します。 メニュー項目またはツール バー ボタンでマウスのクリックで、またはキーの組み合わせによっては、コマンドが生成されます。 ユーザーはたとえば、Windows メッセージを生成し、移動するか、ウィンドウのサイズを変更します。 その他の Windows メッセージは、windows を取得または、フォーカスが失われ、プログラムの起動や終了などのイベントが発生したときに送信されます。 コントロール通知メッセージは、マウスのクリックや ダイアログ ボックスでボタンやリスト ボックス コントロールなどのコントロールでの他のユーザー操作によって生成されます。  
  
 `Run`クラスのメンバー関数`CWinApp`メッセージを取得し、適切なウィンドウにディスパッチします。 ほとんどのコマンド メッセージは、アプリケーションのメイン フレーム ウィンドウに送信されます。 `WindowProc`クラス ライブラリを取得して、メッセージの定義済みおよび受信したメッセージのカテゴリに応じて、異なる方法で、それらをルーティングします。  
  
 これで、プロセスの受信側の一部を検討してください。  
  
 メッセージの受信者となる初期ウィンドウ オブジェクトである必要があります。 Windows メッセージは、そのウィンドウ オブジェクトが直接通常処理されます。 コマンド メッセージは、アプリケーションのメイン フレーム ウィンドウに送信された通常の記載コマンド ターゲット チェーンにルーティング[コマンド ルーティング](../mfc/command-routing.md)です。  
  
 メッセージまたはコマンドを受信できる各オブジェクトには、独自のメッセージがメッセージまたはそのハンドラーの名前を持つコマンド マップがあります。  
  
 コマンド ターゲット オブジェクトがメッセージまたはコマンドを受信すると、一致するものをメッセージ マップを検索します。 メッセージのハンドラーが見つかると、ハンドラーを呼び出します。 メッセージ マップを検索する方法の詳細については、次を参照してください。[方法、フレームワークのメッセージ マップ検索](../mfc/how-the-framework-searches-message-maps.md)です。 図をもう一度参照[フレームワークにおけるコマンド](../mfc/user-interface-objects-and-command-ids.md)です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

