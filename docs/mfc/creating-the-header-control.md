---
title: ヘッダー コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: fdb96eee243214d053a8f375f742cf69aa4e512d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568464"
---
# <a name="creating-the-header-control"></a>ヘッダー コントロールの作成

ヘッダー コントロールは、ダイアログ エディターで直接利用はありません (ただし、ヘッダー コントロールを含む、リスト コントロールを追加することができます)。

### <a name="to-put-a-header-control-in-a-dialog-box"></a>ダイアログ ボックスで、ヘッダー コントロールを配置するには

1. 型のメンバー変数を手動で埋め込む[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)ダイアログ クラスにします。

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、作成し、スタイルを設定、 `CHeaderCtrl`、配置、および、それを表示します。

1. ヘッダー コントロールに項目を追加します。

1. 使用ダイアログ クラスのハンドラー関数をマップする任意のヘッダー コントロール通知メッセージの [プロパティ] ウィンドウを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>ヘッダー コントロールを表示 (CListView されません) に配置するには

1. 埋め込みを[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)ビュー クラスのオブジェクト。

1. スタイル、位置、およびビューのヘッダー コントロールのウィンドウを表示[OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)メンバー関数。

1. ヘッダー コントロールに項目を追加します。

1. 使用にビュー クラスのハンドラー関数をマップする任意のヘッダー コントロール通知メッセージのプロパティ ウィンドウを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。

どちらの場合は、ビューまたはダイアログのオブジェクトが作成されたときに埋め込まれたコントロール オブジェクトが作成されます。 呼び出す必要がありますし、 [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)コントロール ウィンドウを作成します。 コントロールを配置するには、呼び出す[わけ](../mfc/reference/cheaderctrl-class.md#layout)コントロールの初期サイズと位置を決定して[SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)目的の位置を設定します。 」の説明に従って項目を追加[ヘッダー コントロールへの項目の追加](../mfc/adding-items-to-the-header-control.md)します。

詳細については、次を参照してください。[ヘッダー コントロールを作成する](/windows/desktop/Controls/header-controls)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

