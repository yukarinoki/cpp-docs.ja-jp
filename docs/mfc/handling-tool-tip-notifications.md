---
title: ツール ヒントの通知の処理
ms.date: 11/04/2016
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
ms.openlocfilehash: 973c4a12f3b3bdc91269736874b7193130290a76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548916"
---
# <a name="handling-tool-tip-notifications"></a>ツール ヒントの通知の処理

指定した場合、 **TBSTYLE_TOOLTIPS**ツールバーのスタイルを作成し、ツール ヒント コントロールを管理します。 ツール ヒントは、ツール バー ボタンを説明するテキストの行を格納する小さなポップアップ ウィンドウです。 ツール ヒントが非表示され場合にのみ、ユーザー ツール バー ボタン上にカーソルを置きます約半分のままに 2 つ目を表示します。 カーソルの近くにツール ヒントが表示されます。

ツール ヒントが表示される前に、 **TTN_NEEDTEXT**通知メッセージは、ボタンのわかりやすいテキストを取得するツールバーのオーナー ウィンドウに送信されます。 ツールバーのオーナー ウィンドウがある場合、`CFrameWnd`余分に労力、ヒントが表示されますので、ツール ウィンドウで、`CFrameWnd`の既定のハンドラーを持つ、 **TTN_NEEDTEXT**通知します。 ツールバーのオーナー ウィンドウがから派生していないかどうかは`CFrameWnd`、ダイアログ ボックスまたはフォーム ビューなどはする必要があります、オーナー ウィンドウのメッセージ マップにエントリを追加し、メッセージ マップでの通知ハンドラーを提供します。 オーナー ウィンドウのメッセージ マップ エントリは次のとおりです。

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]

## <a name="remarks"></a>Remarks

*memberFxn*<br/>
このボタンのテキストが必要なときに呼び出されるメンバー関数。

ツール ヒントの id は常に 0 です。

加え、 **TTN_NEEDTEXT**通知では、ツール ヒント コントロール通知を送信できます、次をツール バー コントロール。

|通知|説明|
|------------------|-------------|
|**TTN_NEEDTEXTA**|ツール ヒント コントロールには、ASCII テキスト (Windows 95 の場合のみ) が必要です。|
|**TTN_NEEDTEXTW**|ツール ヒント コントロールには、UNICODE テキスト (Windows NT のみ) が必要です。|
|**TBN_HOTITEMCHANGE**|ホットの (強調表示されている) アイテムが変更されたことを示します。|
|**NM_RCLICK**|ユーザーがボタンを右クリックを示します。|
|**TBN_DRAGOUT**|ユーザーがボタンをクリックし、ボタンからポインターをドラッグすることを示します。 これにより、アプリケーションがドラッグを実装して、ツール バー ボタンから削除できます。 この通知を受信するときに、アプリケーションは、ドラッグを開始し、ドロップ操作。|
|**TBN_DROPDOWN**|ユーザーが使用しているボタンをクリックしたことを示します、 **TBSTYLE_DROPDOWN**スタイル。|
|**TBN_GETOBJECT**|ユーザーがポインターを使用しているボタンの上に移動することを示します、 **TBSTYLE_DROPPABLE**スタイル。|

ハンドラー関数の例とツール ヒントを有効にする方法の詳細については、次を参照してください。[ツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)します。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

