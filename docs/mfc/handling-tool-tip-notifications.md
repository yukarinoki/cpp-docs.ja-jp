---
title: ツール ヒントの通知の処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b9dffa2513c11a5feb3228cb4fdb1f6efbebe7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="handling-tool-tip-notifications"></a>ツール ヒントの通知の処理
指定すると、`TBSTYLE_TOOLTIPS`スタイル、ツールバーを作成し、ツール ヒント コントロールを管理します。 ツール ヒントは、ツールバーのボタンを説明するテキストの行を含む小さなポップアップ ウィンドウです。 ツール ヒントが非表示、および表示されるだけと、ユーザー ツール バー ボタン上にカーソルを置きます 2 つ目の約半分ままにします。 ツール ヒントは、カーソルの近くに表示されます。  
  
 ツール ヒントが表示される前に、 **TTN_NEEDTEXT**ボタンのわかりやすいテキストを取得するツールバーのオーナー ウィンドウに通知メッセージを送信します。 ツールバーのオーナー ウィンドウがある場合、`CFrameWnd`ウィンドウで、ツール ヒントが表示されて、余分な作成作業なし`CFrameWnd`の既定のハンドラーを持つ、 **TTN_NEEDTEXT**通知します。 ツールバーのオーナー ウィンドウがから派生していないかどうかは`CFrameWnd`、 ダイアログ ボックスやフォーム ビューなどには、オーナー ウィンドウのメッセージ マップにエントリを追加し、メッセージ マップに通知ハンドラーを提供する必要があります。 オーナー ウィンドウのメッセージ マップ エントリは次のとおりです。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]  
  
## <a name="remarks"></a>コメント  
 `memberFxn`  
 このボタンのテキストが必要なときに呼び出されるメンバー関数。  
  
 なお、ツール ヒントの id は常に 0 です。  
  
 加え、 **TTN_NEEDTEXT**通知には、ツール ヒント コントロールの次通知を送信する、ツール バー コントロール。  
  
|通知|説明|  
|------------------|-------------|  
|**TTN_NEEDTEXTA**|ツール ヒント コントロールには、ASCII テキスト (Windows 95) が必要です。|  
|**TTN_NEEDTEXTW**|ツール ヒント コントロールには、UNICODE テキスト (Windows NT) が必要です。|  
|**TBN_HOTITEMCHANGE**|ホット (強調表示されている) アイテムが変更されたことを示します。|  
|**NM_RCLICK**|ユーザーがボタンを右クリックしたことを示します。|  
|**TBN_DRAGOUT**|ユーザーがボタンをクリックし、ボタンからポインターをドラッグすることを示します。 これにより、ドラッグを実装して、ツール バー ボタンから削除するアプリケーション。 この通知を受信するときに、アプリケーションはドラッグを開始し、操作を削除します。|  
|**TBN_DROPDOWN**|ユーザーが使用しているボタンをクリックしたことを示します、 **TBSTYLE_DROPDOWN**スタイル。|  
|**TBN_GETOBJECT**|ユーザーを使用するボタンの上、ポインターを移動することを示します、 **TBSTYLE_DROPPABLE**スタイル。|  
  
 ハンドラー関数の例とツール ヒントを有効にする方法の詳細については、次を参照してください。[ツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

