---
title: コマンド メッセージのハンドラー方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5c38a1d4294993170cfeff64be6a83700fa7497
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373439"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>コマンド以外のメッセージのハンドラー検索方法

コマンドとは異なりは、標準 Windows メッセージは、チェーン コマンド ターゲットでルーティングされませんが、Windows メッセージを送信する先のウィンドウで、通常は処理されます。 メイン フレーム ウィンドウ、MDI 子ウィンドウ、標準のコントロール、ダイアログ ボックス、ビュー、または他の種類の子ウィンドウのウィンドウがあります。

実行時に、各 Windows ウィンドウがウィンドウのオブジェクトにアタッチ (から直接または間接的に派生した`CWnd`) を持つ独自の関連付けられているメッセージ マップおよびハンドラー関数。 フレームワークは、メッセージ マップを使用: コマンドと、メッセージの受信ハンドラーをマッピングします。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

