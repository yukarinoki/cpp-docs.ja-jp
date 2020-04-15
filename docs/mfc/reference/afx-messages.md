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
ms.openlocfilehash: b4ed86c11d3c5b5f1ce38e3146533109f3a6b00d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363594"
---
# <a name="afx-messages"></a>AFX メッセージ

これらのメッセージは MFC で使用されます。

## <a name="messages"></a>メッセージ

次の表は、MFC ライブラリで使用されるメッセージの一覧です。

||||||
|-|-|-|-|-|
|Message|説明|[in]*wパラム*|*lParam* (特に明記されていない限り、すべてのパラメータは[in]です。|戻り値|
|AFX_WM_ACCGETOBJECT|使用されていません。|使用されていません。|適用不可。|適用不可。|
|AFX_WM_ACCGETSTATE|ユーザー補助のサポートに使用されます。 このメッセージを`CMFCPopupMenu`送信するか`CMFCRibbonPanelMenu`、現在の要素の状態を取得します。|メニュー ボタンまたは区切り記号である要素のインデックス。|使用されていません。|要素の状態。 インデックスが無効な場合は -1、メニュー ボタンに特別な属性がない場合は 0 です。 それ以外の場合は、次のフラグの組み合わせです。<br /><br /> TBBS_DISABLED — アイテムが無効になっています<br /><br /> TBBS_CHECKED — 項目がチェックされます<br /><br /> TBBS_BUTTON — 品目は標準押ボタンです<br /><br /> TBBS_PRESSED — ボタンが押された状態<br /><br /> TBBS_INDETERMINATE — 未定義の状態<br /><br /> TBBS_SEPARATOR - メニューボタンではなく、この要素は他のメニュー項目間の分離を形成します。|
|AFX_WM_CHANGE_ACTIVE_TAB|フレームワークは、このメッセージを、大きめのコントロール バー コントロールに送信します。 ユーザーがアクティブなタブを変更`CMFCTabCtrl`したときにオブジェクトから通知を受け取る場合は、このメッセージを処理します。|タブのインデックス。|使用されていません。|ゼロ以外の値。|
|AFX_WM_CHANGE_CURRENT_FOLDER|フレームワークは、ユーザーが現在の`CMFCShellListCtrl`フォルダーを変更した場合の親にこのメッセージを送信します。|使用されていません。|使用されていません。|使用されていません。|
|AFX_WM_CHANGEVISUALMANAGER|フレームワークは、ユーザーが現在のビジュアル マネージャーを変更するときに、すべてのフレーム ウィンドウにこのメッセージを送信します。 このメッセージに対して、フレーム ウィンドウは領域を再計算し、必要に応じて他のパラメータを調整します。 このイベントに関する通知を受け取る必要がある場合は、アプリケーションでAFX_WM_CHANGEVISUALMANAGER メッセージを処理できます。 このイベントのフレームワークの内部処理が`OnChangeVisualManager`確実に行われるように、基本クラス ハンドラー ( ) を呼び出す必要があります。|使用されていません。|使用されていません。|使用されていません。|
|AFX_WM_CHANGING_ACTIVE_TAB|オブジェクトの`CMFCTabCtrl`親に送信されます。  ユーザーがタブをリセットしたときにオブジェクトから`CMFCTabCtrl`通知を受信する場合は、このメッセージを処理します。|アクティブ化されているタブのインデックス。|使用されていません。|ゼロ以外の値。|
|AFX_WM_CHECKEMPTYMINIFRAME|内部使用専用です。|適用不可。|適用不可。|適用不可。|
|AFX_WM_CREATETOOLBAR|ユーザー`CMFCToolBarsListPropertyPage`がカスタマイズ プロセス中に新しいツール バーを作成したときに送信されます。 このメッセージを処理して、カスタム CMFCToolBar 派生オブジェクトをインスタンス化できます。 このメッセージを処理して独自のツール バーを作成する場合は、既定のハンドラーの呼び出しを省略します。|使用されていません。|ツール バーの名前を含む文字列へのポインター。|新しく作成されたツール バーへのポインター。 NULL は、ツールバーの作成がキャンセルされたことを示します。|
|AFX_WM_CUSTOMIZEHELP|ユーザーが`CMFCToolbarCustomize Dialog`**[ヘルプ**] ボタンまたは F1 キーを押したときに、カスタマイズ プロパティ シートからメイン フレーム ウィンドウに送信されます。|カスタマイズ プロパティ シートのアクティブ なページを指定します。|`CMFCToolbarCustomize Dialog` オブジェクトを指すポインターです。|ゼロ。|
|AFX_WM_CUSTOMIZETOOLBAR|この`CMFCToolbarCustomize Dialog`メッセージを送信して、ユーザーが新しいツール バーを作成していることを親フレームに通知します。|カスタマイズが開始された場合は TRUE、カスタマイズが完了すると FALSE。|使用されていません。|ゼロ。|
|AFX_WM_DELETETOOLBAR|ユーザーがカスタマイズ モードでツール バーを削除しようとしているときに、メイン フレーム ウィンドウに送信されます。<br /><br /> ユーザーがカスタマイズ モードでツール バーを削除したときに追加のアクションを実行するには、このメッセージを処理します。 また、ツール バーを削除する`OnToolbarDelete`既定のハンドラー ( ) を呼び出す必要もあります。 既定のハンドラーは、ツール バーを削除できるかどうかを示す値を返します。|使用されていません。|削除する`CMFCToolBar`オブジェクトへのポインター。|ツールバーを削除できない場合は 0 以外の値を指定します。それ以外の場合は 0。|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`このメッセージをメイン フレーム ウィンドウに送信して、ドキュメントの色を取得します。|使用されていません。|[イン、アウト]`CList<COLORREF, COLORREF>`オブジェクトへのポインター。|ゼロ。|
|AFX_WM_GETDRAGBOUNDS|内部使用専用です。|適用不可。|適用不可。|適用不可。|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|ユーザーがリボン リスト アイテムを強調表示したときに、メイン フレーム ウィンドウに送信されます。|強調表示された項目のインデックス|へのポインタ`CMFCBaseRibbonElement`|使用されていません。|
|AFX_WM_ON_AFTER_SHELL_COMMAND|ユーザーがシェル コマンド`CMFCShellListCtrl`の`CMFCShellTreeCtrl`実行を終了したときに、または の親コントロールに送信されます。|ユーザーが実行したコマンドの ID|使用されていません。|アプリケーションがこのメッセージを処理する場合は、ゼロを返す必要があります。|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|フレームワークは、ポップアップ メニューを表示する前に、このメッセージをリボンの親に送信します。 このメッセージを処理し、ポップアップ メニューをいつでも変更できます。|使用されていません。|へのポインタ`CMFCBaseRibbonElement`|使用されていません。|
|AFX_WM_ON_CANCELTABMOVE|内部使用専用です。|適用不可。|適用不可。||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|ユーザーがアクティブなリボン コントロールのカテゴリを変更すると、フレームワークはメイン フレームにこのメッセージを送信します。|使用されていません。|カテゴリが変更された`CMFCRibbonBar`を指すポインター。|使用されていません。|
|AFX_WM_ON_CLOSEPOPUPWINDOW|フレームワークは、ウィンドウが閉じようとしている`CMFCDesktopAlertWnd`ことを所有者に通知するために、このメッセージを送信します。|使用されていません。|オブジェクトへの`CMFCDesktopAlertWnd`ポインター。|使用されていません。|
|AFX_WM_ON_DRAGCOMPLETE|内部使用専用です。|適用不可。|適用不可。|適用不可。|
|AFX_WM_ON_GET_TAB_TOOLTIP|カスタム ツールヒントが有効になっている場合、タブ ウィンドウがタブのツールヒントを表示する際に、メイン フレーム ウィンドウに送信されます。|使用されていません。|`CMFCTabToolTipInfo`構造体へのポインター。|使用されていません。|
|AFX_WM_ON_HSCROLL|変更可能なコントロール バー コントロールに送信されます。 タブ付きウィジェットの水平スクロール`CMFCTabCtrl`バーでスクロール イベントが発生したときに、オブジェクトから通知を受け取るこのメッセージを処理します。|下位ワードは、ユーザーのスクロール要求を示すスクロール バーの値を指定します。  詳細については、このトピックで後に示す表を参照してください。|使用されていません。|ゼロ以外の値。|
|AFX_WM_ON_MOVE_TAB|ユーザーがタブを新しい位置にドラッグしたときに、タブ付きウィンドウの親に送信されます。|元の位置にあるタブの 0 から始まるインデックス。|[アウト]新しい位置にあるタブの 0 から始まるインデックス。|ゼロ。|
|AFX_WM_ON_MOVETABCOMPLETE|内部使用専用です。|適用不可。|適用不可。|適用不可。|
|AFX_WM_ON_MOVETOTABGROUP|ユーザーが MDI 子ウィンドウをあるタブ付きグループから別のタブ付きグループに移動したときに、メイン フレーム ウィンドウに送信されます。|MDI 子ウィンドウが削除`CMFCTabCtrl`されたタブ付きウィンドウ ( ) へのハンドル。|[アウト]MDI 子ウィンドウが挿入`CMFCTabCtrl`されたタブ付きウィンドウ ( ) へのハンドル。|無視されます。|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|ユーザーがコントロール バー`CDockablePane`のキャプションの **[閉じる**] ボタンをクリックすると、親に送信されます。|使用されていません。|ユーザーが **[閉じる**] ボタンをクリックしたドッキング可能なペインへのポインター。|ペインを閉じることができない場合は TRUE。それ以外の場合は FALSE。|
|AFX_WM_ON_RENAME_TAB|ユーザーが編集可能なタブの名前を変更した後、タブ付きウィンドウの親に送信されます。|名前を変更したタブの 0 から始まるインデックス。|[アウト]新しいタブ名を含む文字列へのポインター。|アプリケーションがこのメッセージを処理する場合は 0 以外。フレームワークは への呼び出`CMFCBaseTabCtrl::SetTabLabel`しを抑制します。  ゼロが返された場合`CMFCBaseTabCtrl::SetTabLabel`は、フレームワークによって呼び出されます。|
|AFX_WM_ON_RIBBON_CUSTOMIZE|ユーザーがカスタマイズを開始したときに親フレームに送信されます。 独自のカスタマイズ ダイアログ ボックスを表示する場合は、このメッセージを処理します。|使用されていません。|カスタマイズするリボン コントロールへのポインター。|アプリケーションがこのメッセージを処理し、独自のカスタマイズ ダイアログ ボックスを表示する場合は、0 以外の値を指定します。 アプリケーションが 0 を返す場合、フレームワークは組み込みのカスタマイズ ダイアログ ボックスを表示します。|
|AFX_WM_ON_TABGROUPMOUSEMOVE|内部使用専用です。|適用不可。|適用不可。|適用不可。|
|AFX_WM_POSTSETPREVIEWFRAME|ユーザーが印刷プレビュー モードを変更したことをメイン フレームに通知するために送信されます|TRUE は、印刷プレビュー モードが設定されていることを示します。 FALSE は、印刷プレビュー モードがオフになっていることを示します。|使用されていません。|使用されていません。|
|AFX_WM_PROPERTY_CHANGED|ユーザーが選択したプロパティの値を変更したときに`CMFCPropertyGridCtrl`、プロパティ グリッド コントロール ( ) の所有者に送信されます。|プロパティ リストのコントロール ID。|変更されたプロパティ (`CMFCPropertyGridProperty`) へのポインター。|使用されていません。|
|AFX_WM_RESETCONTEXTMENU|ユーザーがカスタマイズ中にコンテキスト メニューをリセットしたときに、メイン フレーム ウィンドウに送信されます。|コンテキスト メニューのリソース ID。|現在のコンテキスト メニューへのポインター `CMFCPopupMenu`。|使用されていません。|
|AFX_WM_RESETKEYBOARD|ユーザーがカスタマイズ中にすべてのキーボード アクセラレータをリセットすると、フレームワークはメイン フレーム ウィンドウにこのメッセージを送信します。|使用されていません。|使用されていません。|使用されていません。|
|AFX_WM_RESETMENU|ユーザーがカスタマイズ中にアプリケーション フレーム メニューをリセットすると、フレームワークはメニューの所有者 (フレーム ウィンドウ) にこのメッセージを送信します。|メニュー リソース ID。|使用されていません。|使用されていません。|
|AFX_WM_RESETPROMPT|ユーザーがツール バーのカスタマイズ ダイアログ ボックスからツール バーをリセットすると、フレームワークがこのメッセージを送信します。 既定のハンドラーは、ユーザーがツール バーをリセットするかどうかを確認するメッセージ ボックスを表示します。|使用されていません。|使用されていません。|使用されていません。|
|AFX_WM_RESETTOOLBAR|オブジェクト`CMFCToolBar`は、ツール バーが元の状態に復元されると、つまりリソースから読み込まれるときにこのメッセージを送信します。 このメッセージを処理して、クラスが 派生`CMFCToolbarButton`したツール バー ボタンを挿入し直します。 詳細については、「`CMFCToolbarComboBoxButton`」を参照してください。|状態が復元されたツール バーのリソース ID。|使用されていません。|ゼロ。|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`オブジェクトは、ユーザーが通常のメニュー ボタンをクリックすると、その所有者にこのメッセージを送信します。 ユーザーがボタンをクリックしたときに、ポップアップ`CMFCToolbarMenuButton`メニューを表示するために使用するたびに、このメッセージを処理します。|メッセージを送信するボタンのコマンド ID。|カーソルの画面座標。 下位の単語は、x 座標を指定します。 上位ワードは y 座標を指定します。|使用されていません。|
|AFX_WM_TOOLBARMENU|マウス ポインターがペインのクライアント領域または非クライアント領域にあるときに、マウスの右ボタンを離したときに、メイン フレーム ウィンドウに送信されます。|使用されていません。|マウス ポインターの画面座標。 下位の単語は、x 座標を指定します。 上位ワードは y 座標を指定します。|アプリケーションがこのメッセージを処理する場合はゼロ。それ以外の場合は、0 以外の値を返します。|
|AFX_WM_UPDATETOOLTIPS|すべてのツールヒントの所有者に送信され、ツールヒント コントロールを再作成する必要があることを示します。|このメッセージを処理するコントロールの種類。 使用可能な値のリストについては、このトピックの後の表を参照してください。|使用されていません。|使用されていません。|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`ユーザーが **[ヘルプ**] ボタンをクリックするか、ヘルプ**キャプション**ボタンまたは F1 キーをクリックしてヘルプ モードに入ると、このメッセージが親フレームに送信されます。|使用されていません。|のインスタンスへのポインター `CMFCWindowsManagerDialog`。|使用されていません。|

次の表は、AFX_WM_HSCROLLメソッドの*lParam*パラメータの下位ワードの値を示しています。

|||
|-|-|
|[値]|意味|
|SB_ENDSCROLL|ユーザーがスクロールを終了します。|
|SB_LEFT|ユーザーが左上にスクロールします。|
|SB_RIGHT|ユーザーが右下にスクロールします。|
|SB_LINELEFT|ユーザーは 1 単位ずつ左にスクロールします。|
|SB_LINERIGHT|ユーザーは 1 単位ずつ右にスクロールします。|
|SB_PAGELEFT|ユーザーは、ウィンドウの幅で左にスクロールします。|
|SB_PAGERIGHT|ユーザーは、ウィンドウの幅を右にスクロールします。|
|SB_THUMBPOSITION|ユーザーがスクロール ボックス (つまみ) をドラッグし、マウス ボタンを離しました。 上位ワードは、ドラッグ操作の最後のスクロール ボックスの位置を示します。|
|SB_THUMBTRACK|ユーザーがスクロール ボックスをドラッグしています。 AFX_WM_ON_HSCROLL メッセージは、ユーザーがマウス ボタンを離すまで、この値を使用して繰り返し送信されます。 上位ワードは、スクロール ボックスがドラッグされた位置を示します。|

> [!NOTE]
> *lParam*パラメータの上位ワードは、下位ワードがSB_THUMBPOSITIONまたはSB_THUMBTRACKの場合に、スクロール ボックスの現在位置を指定します。それ以外の場合、この語は使用されません。

次の表は、AFX_WM_UPDATETOOLTIPSメッセージの*lParam*パラメータのフラグ値を示しています。

|||
|-|-|
|フラグ|[値]|
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
