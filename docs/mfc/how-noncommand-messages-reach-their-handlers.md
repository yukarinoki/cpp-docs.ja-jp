---
title: 非コマンドのメッセージのハンドラー検索方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 3999c74bf7a612acb998e7a044c12948d7679d9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343883"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>コマンド以外のメッセージのハンドラー検索方法
コマンドとは異なり標準 Windows メッセージは、チェーン コマンド ターゲットを通じてルーティングされませんが、Windows メッセージを送信する先ウィンドウによって処理される通常。 ウィンドウには、メイン フレーム ウィンドウ、MDI 子ウィンドウ、標準のコントロール、ダイアログ ボックス、ビュー、またはその他の何らかの子ウィンドウがあります。  
  
 実行時に、Windows の各ウィンドウがウィンドウのオブジェクトにアタッチ (から直接または間接的に派生`CWnd`) を持つ独自の関連するメッセージ マップおよびハンドラー関数。 フレームワークは、メッセージ マップを使用: コマンドです: 受信メッセージをハンドラーにマップします。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

