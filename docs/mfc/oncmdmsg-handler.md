---
title: OnCmdMsg ハンドラー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnCmdMsg
dev_langs:
- C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6691e4935d46b32bc8f433823888bb7f53a36890
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398834"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg ハンドラー

各コマンド ターゲットを呼び出すコマンドのルーティングを実現する、`OnCmdMsg`次のコマンド ターゲット シーケンス内のメンバー関数。 コマンドの使用対象`OnCmdMsg`コマンドを処理できるかどうかを判断し、処理できない場合は、別のコマンド ターゲットにルーティングします。

コマンド ターゲット クラスごとのオーバーライド、`OnCmdMsg`メンバー関数。 上書きは、次のターゲットを特定する各クラスのルート コマンドを使用できます。 フレーム ウィンドウでは、たとえば、常にコマンドをルーティングする現在の子ウィンドウまたはビューの表に示すように[標準のコマンド ルート](../mfc/command-routing.md)します。

既定の`CCmdTarget`の実装`OnCmdMsg`コマンド ターゲット クラスのメッセージ マップを使用して受信する各コマンド メッセージのハンドラー関数の検索-標準的なメッセージを検索することと同じ方法でします。 一致が見つかると、ハンドラーを呼び出します。 メッセージ マップの検索については[方法、フレームワークのメッセージ マップ検索](../mfc/how-the-framework-searches-message-maps.md)します。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

