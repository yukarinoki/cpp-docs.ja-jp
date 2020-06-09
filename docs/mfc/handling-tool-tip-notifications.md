---
title: ツール ヒントの通知の処理
ms.date: 11/04/2016
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
ms.openlocfilehash: 41e3dbfc2269f5fbf3c12dc00c19f8a2253fd16a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626442"
---
# <a name="handling-tool-tip-notifications"></a>ツール ヒントの通知の処理

**TBSTYLE_TOOLTIPS**スタイルを指定すると、ツールバーはツールヒントコントロールを作成して管理します。 ツールヒントは、ツールバーボタンを説明するテキスト行を含む小さなポップアップウィンドウです。 ツールヒントは表示されません。ユーザーがツールバーボタンにカーソルを置いたときに表示され、約 1 0.5 秒間はその位置に置かれます。 ツールヒントはカーソルの近くに表示されます。

ツールヒントが表示される前に、ツールバーのオーナーウィンドウに**TTN_NEEDTEXT**通知メッセージが送信され、ボタンの説明テキストが取得されます。 ツールバーの [オーナー] ウィンドウがウィンドウの場合、 `CFrameWnd` 追加の作業を行わずにツールヒントが表示され `CFrameWnd` ます。には**TTN_NEEDTEXT**通知の既定のハンドラーがあるためです。 ツールバーのオーナーウィンドウがダイアログボックスやフォームビューなどから派生していない場合は、 `CFrameWnd` オーナーウィンドウのメッセージマップにエントリを追加し、メッセージマップに通知ハンドラーを提供する必要があります。 オーナーウィンドウのメッセージマップへのエントリは次のとおりです。

[!code-cpp[NVC_MFCControlLadenDialog#40](codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]

## <a name="remarks"></a>Remarks

*memberFxn*<br/>
このボタンにテキストが必要な場合に呼び出されるメンバー関数。

ツールヒントの id は常に0であることに注意してください。

ツールヒントコントロールは、 **TTN_NEEDTEXT**通知に加えて、次の通知を toolbar コントロールに送信できます。

|通知|意味|
|------------------|-------------|
|**TTN_NEEDTEXTA**|ツールヒントコントロールには ASCII テキストが必要です (Windows 95 のみ)|
|**TTN_NEEDTEXTW**|ツールヒントコントロールには UNICODE テキストが必要です (Windows NT のみ)|
|**TBN_HOTITEMCHANGE**|ホット (強調表示) 項目が変更されたことを示します。|
|**NM_RCLICK**|ユーザーがボタンを右クリックしたことを示します。|
|**TBN_DRAGOUT**|ユーザーがボタンをクリックし、ポインターをボタンの外にドラッグしたことを示します。 これにより、アプリケーションは、ツールバーボタンからドラッグアンドドロップを実装できます。 この通知を受信すると、アプリケーションはドラッグアンドドロップ操作を開始します。|
|**TBN_DROPDOWN**|ユーザーが**TBSTYLE_DROPDOWN**スタイルを使用するボタンをクリックしたことを示します。|
|**TBN_GETOBJECT**|ユーザーが**TBSTYLE_DROPPABLE**スタイルを使用するボタンの上にポインターを移動したことを示します。|

ハンドラー関数の例と、ツールヒントを有効にする方法の詳細については、「[ツールヒント](tool-tips-in-windows-not-derived-from-cframewnd.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](using-ctoolbarctrl.md)<br/>
[制限](controls-mfc.md)
