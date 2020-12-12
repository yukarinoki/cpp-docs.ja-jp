---
description: 詳細については、「非コマンドメッセージのハンドラーへの対応」を参照してください。
title: コマンド以外のメッセージのハンドラー検索方法
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: e337a62a731e7ed0832b6cd28d1f56024247c176
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172818"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>コマンド以外のメッセージのハンドラー検索方法

コマンドとは異なり、標準の Windows メッセージはコマンドターゲットのチェーン経由ではルーティングされませんが、通常は Windows がメッセージを送信するウィンドウによって処理されます。 ウィンドウには、メインフレームウィンドウ、MDI 子ウィンドウ、標準コントロール、ダイアログボックス、ビュー、その他の種類の子ウィンドウなどがあります。

実行時には、各ウィンドウは、 `CWnd` 独自のメッセージマップおよびハンドラー関数を持つウィンドウオブジェクト (から直接または間接的に派生) にアタッチされます。 フレームワークでは、コマンドの場合と同様に、メッセージマップを使用して、受信メッセージをハンドラーにマップします。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)
