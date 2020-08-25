---
title: AFX メッセージ
ms.date: 11/04/2016
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
ms.openlocfilehash: 409760eff6ba6b31413c11fb45ea91a6d07b9485
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832400"
---
# <a name="afx-messages"></a>AFX メッセージ

これらのメッセージは MFC で使用されます。

## <a name="messages"></a>メッセージ

次の表に、MFC ライブラリで使用されるメッセージの一覧を示します。

|Message|説明|から *wParam*|*lParam* (特に明記されていない限り、すべてのパラメーターは [in] です)。|戻り値|
|-|-|-|-|-|
|AFX_WM_ACCGETOBJECT|使用しません。|使用しません。|適用不可。|適用不可。|
|AFX_WM_ACCGETSTATE|ユーザー補助機能のサポートに使用されます。 `CMFCPopupMenu` `CMFCRibbonPanelMenu` 現在の要素の状態を取得するには、このメッセージをまたはに送信します。|要素のインデックス。メニューボタンまたは区切り記号を指定できます。|使用されていません。|要素の状態。 インデックスが無効である場合は-1 になります。メニューボタンに特別な属性がない場合は0になります。 それ以外の場合は、次のフラグの組み合わせです。<br /><br /> TBBS_DISABLED-項目が無効です<br /><br /> TBBS_CHECKED-項目がオンになっています<br /><br /> TBBS_BUTTON —項目は標準のプッシュボタンです<br /><br /> TBBS_PRESSED-ボタンが押されています<br /><br /> TBBS_INDETERMINATE —未定義の状態<br /><br /> TBBS_SEPARATOR-メニューボタンではなく、この要素は他のメニュー項目間の分離を形成します。|
|AFX_WM_CHANGE_ACTIVE_TAB|フレームワークは、このメッセージをサイズ変更可能コントロールバーコントロールに送信します。 このメッセージを処理して `CMFCTabCtrl` 、ユーザーがアクティブなタブを変更したときにオブジェクトから通知を受信します。|タブのインデックス。|使用されていません。|なら.|
|AFX_WM_CHANGE_CURRENT_FOLDER|フレームワークは、ユーザーが現在のフォルダーを変更したときに、の親にこのメッセージを送信し `CMFCShellListCtrl` ます。|使用しません。|使用しません。|使用しません。|
|AFX_WM_CHANGEVISUALMANAGER|フレームワークは、ユーザーが現在のビジュアルマネージャーを変更したときに、すべてのフレームウィンドウにこのメッセージを送信します。 このメッセージに対する応答として、フレームウィンドウはその領域を再計算し、必要に応じて他のパラメーターを調整します。 このイベントについて通知する必要がある場合は、アプリケーションで AFX_WM_CHANGEVISUALMANAGER メッセージを処理することができます。 `OnChangeVisualManager`このイベントのフレームワーク内部処理が発生するようにするには、基本クラスハンドラー () を呼び出す必要があります。|使用しません。|使用しません。|使用しません。|
|AFX_WM_CHANGING_ACTIVE_TAB|オブジェクトの親に送信され `CMFCTabCtrl` ます。  `CMFCTabCtrl`ユーザーがタブをリセットしたときにオブジェクトから通知を受け取る場合は、このメッセージを処理します。|アクティブ化されているタブのインデックス。|使用されていません。|なら.|
|AFX_WM_CHECKEMPTYMINIFRAME|内部使用のみ。|適用不可。|適用不可。|適用不可。|
|AFX_WM_CREATETOOLBAR|`CMFCToolBarsListPropertyPage`カスタマイズプロセス中にユーザーが新しいツールバーを作成したときに送信されます。 このメッセージを処理して、カスタム CMFCToolBar の派生オブジェクトをインスタンス化できます。 このメッセージを処理して独自のツールバーを作成する場合は、既定のハンドラーの呼び出しを省略します。|使用されていません。|ツールバーの名前を格納している文字列へのポインター。|新しく作成されたツールバーへのポインター。 NULL は、ツールバーの作成がキャンセルされたことを示します。|
|AFX_WM_CUSTOMIZEHELP|`CMFCToolbarCustomize Dialog`ユーザーが [**ヘルプ**] ボタンまたは F1 キーを押したときに、カスタマイズプロパティシートからメインフレームウィンドウに送信されます。|カスタマイズプロパティシートのアクティブページを指定します。|`CMFCToolbarCustomize Dialog` オブジェクトを指すポインターです。|ゼロ。|
|AFX_WM_CUSTOMIZETOOLBAR|は、 `CMFCToolbarCustomize Dialog` ユーザーが新しいツールバーを作成していることを親フレームに通知するために、このメッセージを送信します。|カスタマイズが開始された場合は TRUE、カスタマイズが終了した場合は FALSE。|使用されていません。|ゼロ。|
|AFX_WM_DELETETOOLBAR|ユーザーがカスタマイズモードでツールバーを削除しようとしているときに、メインフレームウィンドウに送信されます。<br /><br /> ユーザーがカスタマイズモードでツールバーを削除したときに追加のアクションを実行するには、このメッセージを処理します。 また、既定のハンドラー () を呼び出す必要があり `OnToolbarDelete` ます。これにより、ツールバーが削除されます。 既定のハンドラーは、ツールバーを削除できるかどうかを示す値を返します。|使用されていません。|削除するオブジェクトへのポインター `CMFCToolBar` 。|ツールバーを削除できない場合は0以外。それ以外の場合は0です。|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` このメッセージをメインフレームウィンドウに送信して、ドキュメントの色を取得します。|使用されていません。|[入力、出力]オブジェクトへのポインター `CList<COLORREF, COLORREF>` 。|ゼロ。|
|AFX_WM_GETDRAGBOUNDS|内部使用のみ。|適用不可。|適用不可。|適用不可。|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|ユーザーがリボンリスト項目を強調表示したときにメインフレームウィンドウに送信されます。|強調表示された項目のインデックス|へのポインター `CMFCBaseRibbonElement`|使用されていません。|
|AFX_WM_ON_AFTER_SHELL_COMMAND|`CMFCShellListCtrl` `CMFCShellTreeCtrl` ユーザーがシェルコマンドの実行を終了したときに、またはコントロールの親に送信されます。|ユーザーが実行したコマンドの ID|使用されていません。|アプリケーションがこのメッセージを処理する場合は、0を返します。|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|フレームワークは、ポップアップメニューを表示する前に、このメッセージをリボンの親に送信します。 このメッセージを処理し、ポップアップメニューをいつでも変更できます。|使用されていません。|へのポインター `CMFCBaseRibbonElement`|使用されていません。|
|AFX_WM_ON_CANCELTABMOVE|内部使用のみ。|適用不可。|適用不可。||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|フレームワークは、ユーザーがアクティブなリボンコントロールのカテゴリを変更したときに、このメッセージをメインフレームに送信します。|使用されていません。|カテゴリが変更されたへのポインター `CMFCRibbonBar` 。|使用されていません。|
|AFX_WM_ON_CLOSEPOPUPWINDOW|フレームワークは、ウィンドウが閉じようとしていることを所有者に通知するために、このメッセージを送信し `CMFCDesktopAlertWnd` ます。|使用されていません。|オブジェクトへのポインター `CMFCDesktopAlertWnd` 。|使用されていません。|
|AFX_WM_ON_DRAGCOMPLETE|内部使用のみ。|適用不可。|適用不可。|適用不可。|
|AFX_WM_ON_GET_TAB_TOOLTIP|カスタムツールヒントが有効になっている場合に、タブウィンドウでタブのツールヒントを表示しようとしているときに、メインフレームウィンドウに送信されます。|使用されていません。|構造体へのポインター `CMFCTabToolTipInfo` 。|使用されていません。|
|AFX_WM_ON_HSCROLL|サイズ変更可能コントロールバーコントロールに送信されます。 このメッセージを処理し `CMFCTabCtrl` て、タブ付きウィジェットの水平スクロールバーでスクロールイベントが発生したときにオブジェクトから通知を受信します。|下位ワードは、ユーザーのスクロール要求を示すスクロールバーの値を指定します。  詳細については、このトピックで後に示す表を参照してください。|使用されていません。|なら.|
|AFX_WM_ON_MOVE_TAB|ユーザーがタブを新しい位置にドラッグしたときに、タブ付きウィンドウの親に送信されます。|元の位置にあるタブの0から始まるインデックス。|入出力新しい位置のタブの0から始まるインデックス。|ゼロ。|
|AFX_WM_ON_MOVETABCOMPLETE|内部使用のみ。|適用不可。|適用不可。|適用不可。|
|AFX_WM_ON_MOVETOTABGROUP|ユーザーが MDI 子ウィンドウを1つのタブ付きグループから別のグループに移動したときに、メインフレームウィンドウに送信されます。|`CMFCTabCtrl`MDI 子ウィンドウが削除されたタブ付きウィンドウ () へのハンドル。|入出力`CMFCTabCtrl`MDI 子ウィンドウが挿入されたタブ付きウィンドウ () へのハンドル。|無視されます。|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|`CDockablePane`ユーザーがコントロールバーのキャプションの [**閉じる**] ボタンをクリックしたときに、の親に送信されます。|使用されていません。|ユーザーが [ **閉じる** ] ボタンをクリックしたドッキング可能なペインへのポインター。|ペインを閉じることができない場合は TRUE。それ以外の場合は FALSE。|
|AFX_WM_ON_RENAME_TAB|ユーザーが編集可能なタブの名前を変更した後に、タブ付きウィンドウの親に送信されます。|名前が変更されたタブの0から始まるインデックス。|入出力新しいタブ名を格納している文字列へのポインター。|アプリケーションがこのメッセージを処理する場合は0以外。フレームワークは、の呼び出しを抑制し `CMFCBaseTabCtrl::SetTabLabel` ます。  ゼロが返された場合、 `CMFCBaseTabCtrl::SetTabLabel` はフレームワークによって呼び出されます。|
|AFX_WM_ON_RIBBON_CUSTOMIZE|ユーザーがカスタマイズを開始すると、親フレームに送信されます。 独自のカスタマイズダイアログボックスを表示する場合は、このメッセージを処理します。|使用されていません。|カスタマイズするリボンコントロールへのポインター。|アプリケーションがこのメッセージを処理し、独自のカスタマイズダイアログボックスを表示する場合は0以外の。 アプリケーションが0を返した場合は、フレームワークによって組み込みのカスタマイズダイアログボックスが表示されます。|
|AFX_WM_ON_TABGROUPMOUSEMOVE|内部使用のみ。|適用不可。|適用不可。|適用不可。|
|AFX_WM_POSTSETPREVIEWFRAME|ユーザーが印刷プレビューモードを変更したことをメインフレームに通知するために送信されます|TRUE は、印刷プレビューモードが設定されていることを示します。 FALSE は、印刷プレビューモードがオフになっていることを示します。|使用しません。|使用しません。|
|AFX_WM_PROPERTY_CHANGED|`CMFCPropertyGridCtrl`ユーザーが選択したプロパティの値を変更したときに、プロパティグリッドコントロール () の所有者に送信されます。|プロパティリストのコントロール ID。|変更されたプロパティ () へのポインター `CMFCPropertyGridProperty` 。|使用されていません。|
|AFX_WM_RESETCONTEXTMENU|カスタマイズ中にユーザーがコンテキストメニューをリセットしたときに、メインフレームウィンドウに送信されます。|コンテキストメニューのリソース ID。|現在のコンテキストメニューへのポインター `CMFCPopupMenu` 。|使用されていません。|
|AFX_WM_RESETKEYBOARD|フレームワークは、カスタマイズ中にユーザーがすべてのキーボードアクセラレータをリセットしたときに、メインフレームウィンドウにこのメッセージを送信します。|使用しません。|使用しません。|使用しません。|
|AFX_WM_RESETMENU|カスタマイズ中にユーザーがアプリケーションフレームメニューをリセットしたときに、フレームワークによってこのメッセージがメニュー所有者 (フレームウィンドウ) に送信されます。|メニューリソース ID。|使用しません。|使用しません。|
|AFX_WM_RESETPROMPT|フレームワークは、ユーザーがツールバーの [カスタマイズ] ダイアログボックスからツールバーをリセットしたときに、このメッセージを送信します。 既定のハンドラーには、ユーザーがツールバーをリセットするかどうかを確認するメッセージボックスが表示されます。|使用しません。|使用しません。|使用しません。|
|AFX_WM_RESETTOOLBAR|オブジェクトは、 `CMFCToolBar` ツールバーが元の状態に復元されたとき、つまり、リソースから読み込まれたときに、このメッセージを送信します。 このメッセージを処理して、クラスがから派生したツールバーボタンを再挿入し `CMFCToolbarButton` ます。 詳細については、「`CMFCToolbarComboBoxButton`」を参照してください。|状態が復元されたツールバーのリソース ID。|使用されていません。|ゼロ。|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` オブジェクトは、ユーザーが通常のメニューボタンをクリックしたときに、このメッセージを所有者に送信します。 `CMFCToolbarMenuButton`ユーザーがボタンをクリックしたときにポップアップメニューを表示するために使用するたびに、このメッセージを処理します。|メッセージを送信するボタンのコマンド ID。|カーソルの画面座標。 下位ワードは x 座標を指定します。 上位ワードは y 座標を指定します。|使用されていません。|
|AFX_WM_TOOLBARMENU|マウスポインターがウィンドウのクライアント領域または非クライアント領域内にあるときに、ユーザーがマウスの右ボタンを離すと、メインフレームウィンドウに送信されます。|使用されていません。|マウスポインターの画面座標。 下位ワードは x 座標を指定します。 上位ワードは y 座標を指定します。|アプリケーションがこのメッセージを処理する場合は0。それ以外の場合は0以外の。|
|AFX_WM_UPDATETOOLTIPS|ツールヒントコントロールを再作成する必要があることを示すために、すべてのツールヒントの所有者に送信されます。|このメッセージを処理する必要があるコントロールの種類。 使用可能な値の一覧については、このトピックの後半の表を参照してください。|使用しません。|使用しません。|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` は、ユーザーが [ **ヘルプ** ] ボタンをクリックしたときにこのメッセージを親フレームに送信するか、[ **ヘルプ** キャプション] ボタンまたは F1 キーをクリックしてヘルプモードに入ります。|使用されていません。|のインスタンスへのポインター `CMFCWindowsManagerDialog` 。|使用されていません。|

次の表は、AFX_WM_HSCROLL メソッドの *lParam* パラメーターの下位ワードの値を示しています。

|値|意味|
|-|-|
|SB_ENDSCROLL|ユーザーがスクロールを終了します。|
|SB_LEFT|ユーザーは、左上にスクロールします。|
|SB_RIGHT|ユーザーが右下にスクロールします。|
|SB_LINELEFT|ユーザーは1単位左にスクロールします。|
|SB_LINERIGHT|ユーザーは1単位分だけ右にスクロールします。|
|SB_PAGELEFT|ユーザーはウィンドウの幅で左にスクロールします。|
|SB_PAGERIGHT|ユーザーはウィンドウの幅で右にスクロールします。|
|SB_THUMBPOSITION|ユーザーは、スクロールボックス (つまみ) をドラッグし、マウスボタンを離しました。 上位ワードは、ドラッグ操作の終了時のスクロールボックスの位置を示します。|
|SB_THUMBTRACK|ユーザーがスクロール ボックスをドラッグしています。 AFX_WM_ON_HSCROLL メッセージは、ユーザーがマウスボタンを離すまで、この値と共に繰り返し送信されます。 上位ワードは、スクロールボックスがドラッグされた位置を示します。|

> [!NOTE]
> 順序が低いワードが SB_THUMBPOSITION または SB_THUMBTRACK の場合、 *lParam* パラメーターの上位ワードは、スクロールボックスの現在位置を指定します。それ以外の場合、この単語は使用されません。

次の表に、AFX_WM_UPDATETOOLTIPS メッセージの *lParam* パラメーターのフラグ値を示します。

|フラグ|値|
|-|-|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
