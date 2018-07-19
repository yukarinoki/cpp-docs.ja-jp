---
title: OnIdle メンバー関数は、|Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbe912db448e424f18b6d72f6e148312c5940687
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350368"
---
# <a name="onidle-member-function"></a>OnIdle メンバー関数
Windows メッセージを処理するないときに、フレームワーク、 [CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数は、 [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (MFC ライブラリ リファレンス 』 で説明)。  
  
 オーバーライド`OnIdle`バック グラウンド タスクを実行します。 既定のバージョンでは、ツール バー ボタンなどのユーザー インターフェイス オブジェクトの状態を更新し、その操作の過程で、フレームワークによって作成された一時オブジェクトのクリーンアップを実行します。 次の図は、メッセージ ループを呼び出す方法を示しています。`OnIdle`キューにメッセージがない場合にします。  
  
 ![メッセージのループ プロセス](../mfc/media/vc387c1.gif "vc387c1")  
メッセージ ループ  
  
 詳細については、アイドル ループで何ができる、次を参照してください。[アイドル ループ プロセシング](../mfc/idle-loop-processing.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
