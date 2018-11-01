---
title: コマンド以外のメッセージのハンドラー検索方法
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: f64eb97315b41a314c791e1a4c5bc7721b329fca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545458"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>コマンド以外のメッセージのハンドラー検索方法

コマンドとは異なりは、標準 Windows メッセージは、チェーン コマンド ターゲットでルーティングされませんが、Windows メッセージを送信する先のウィンドウで、通常は処理されます。 メイン フレーム ウィンドウ、MDI 子ウィンドウ、標準のコントロール、ダイアログ ボックス、ビュー、または他の種類の子ウィンドウのウィンドウがあります。

実行時に、各 Windows ウィンドウがウィンドウのオブジェクトにアタッチ (から直接または間接的に派生した`CWnd`) を持つ独自の関連付けられているメッセージ マップおよびハンドラー関数。 フレームワークは、メッセージ マップを使用: コマンドと、メッセージの受信ハンドラーをマッピングします。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

