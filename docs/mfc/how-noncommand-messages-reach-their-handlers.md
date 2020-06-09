---
title: コマンド以外のメッセージのハンドラー検索方法
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: c7b2bf819c5305da4039fae172578298d3b4e609
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618508"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>コマンド以外のメッセージのハンドラー検索方法

コマンドとは異なり、標準の Windows メッセージはコマンドターゲットのチェーン経由ではルーティングされませんが、通常は Windows がメッセージを送信するウィンドウによって処理されます。 ウィンドウには、メインフレームウィンドウ、MDI 子ウィンドウ、標準コントロール、ダイアログボックス、ビュー、その他の種類の子ウィンドウなどがあります。

実行時には、各ウィンドウは、 `CWnd` 独自のメッセージマップおよびハンドラー関数を持つウィンドウオブジェクト (から直接または間接的に派生) にアタッチされます。 フレームワークでは、コマンドの場合と同様に、メッセージマップを使用して、受信メッセージをハンドラーにマップします。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)
