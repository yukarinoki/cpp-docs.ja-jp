---
title: AFX メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc11b3eb79f0d535775f073c772e40c4ed9e822c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355419"
---
# <a name="afx-messages"></a>AFX メッセージ
これらのメッセージは、MFC で使用されます。  
  
## <a name="messages"></a>メッセージ  
 次の表には、MFC ライブラリで使用されているメッセージが表示されます。  
  
||||||  
|-|-|-|-|-|  
|メッセージ|説明|[入力] `wParam`|`lParam` (すべてのパラメーターは、[in] 明記しない限り。)|戻り値|  
|AFX_WM_ACCGETOBJECT|使用しません。|使用しません。|該当なし。|該当なし。|  
|AFX_WM_ACCGETSTATE|ユーザー補助のサポートのために使用します。 このメッセージを送信して`CMFCPopupMenu`または`CMFCRibbonPanelMenu`現在の要素の状態を取得します。|メニュー ボタンまたは区切り記号の場合も、要素のインデックス。|使用しません。|要素の状態。 インデックスが有効でない場合は-1 メニュー ボタンが特別な属性を持っていない場合は 0 です。 それ以外の場合、次のフラグの組み合わせです。<br /><br /> TBBS_DISABLED: 項目が無効になっています<br /><br /> 項目がチェックされて TBBS_CHECKED:<br /><br /> TBBS_BUTTON: 項目が標準のプッシュ ボタンです。<br /><br /> TBBS_PRESSED: ボタンが押されました。<br /><br /> TBBS_INDETERMINATE: 未定義の状態<br /><br /> TBBS_SEPARATOR - ではなくメニュー ボタンでは、他のメニュー項目間の分離をこの要素のフォーム|  
|AFX_WM_CHANGE_ACTIVE_TAB|フレームワークは、このメッセージをサイズ変更可能なコントロール バー コントロールに送信します。 通知を受信するには、このメッセージを処理`CMFCTabCtrl`オブジェクトをユーザーには、アクティブなタブが変更されたときにします。|タブのインデックス。|使用しません。|0 以外。|  
|AFX_WM_CHANGE_CURRENT_FOLDER|フレームワークでは、このメッセージを送信の親に`CMFCShellListCtrl`ユーザーが、現在のフォルダーに変更されたとき。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_CHANGEVISUALMANAGER|フレームワークは、ユーザーが現在のビジュアル マネージャーを変更したときに、すべてのフレーム ウィンドウにこのメッセージを送信します。 このメッセージに応答してでは、フレーム ウィンドウは、領域を再計算し、必要に応じてその他のパラメーターを調整します。 このイベントに関する通知を受ける必要がある場合は、アプリケーションで AFX_WM_CHANGEVISUALMANAGER メッセージを処理できます。 基本クラスのハンドラーを呼び出す必要があります (`OnChangeVisualManager`) フレームワークの内部であることを確認する処理は、このイベントが実行されます。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_CHANGING_ACTIVE_TAB|親に送信される`CMFCTabCtrl`オブジェクト。  通知を受信する場合は、このメッセージを処理`CMFCTabCtrl`オブジェクトをユーザーがタブをリセットします。|アクティブ化しているタブのインデックス。|使用しません。|0 以外。|  
|AFX_WM_CHECKEMPTYMINIFRAME|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_CREATETOOLBAR|送信された`CMFCToolBarsListPropertyPage`カスタマイズ プロセス中に、ユーザーが新しいツールバーを作成するときにします。 カスタム CMFCToolBar から派生したオブジェクトのインスタンスを作成するには、このメッセージを処理することができます。 このメッセージを処理して、独自のツールバーを作成した場合は、既定のハンドラーに呼び出しを省略します。|使用しません。|ツールバーの名前を表す文字列へのポインター。|新しく作成したツールバーへのポインター。 NULL では、ツールバーの作成がキャンセルされたことを示します。|  
|AFX_WM_CUSTOMIZEHELP|カスタマイズのプロパティ シートからメイン フレーム ウィンドウに送信される`CMFCToolbarCustomize Dialog`押されたとき、**ヘルプ**ボタンまたは F1 キーを押す。|カスタマイズのプロパティ シートの現在のページを指定します。|ポインター、`CMFCToolbarCustomize Dialog`オブジェクト。|0 を返します。|  
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog`にユーザーが新しいツールバーを作成すること、親フレームを通知するには、このメッセージを送信します。|`TRUE` カスタマイズが開始されると、`FALSE`カスタマイズが完了するとします。|使用しません。|0 を返します。|  
|AFX_WM_DELETETOOLBAR|ユーザーがカスタマイズ モードでツールバーを削除すると、メイン フレーム ウィンドウに送信されます。<br /><br /> ユーザーがカスタマイズ モードでツールバーを削除すると、多くのアクションを実行するには、このメッセージを処理します。 また、既定のハンドラーを呼び出す必要があります (`OnToolbarDelete`)、ツールバーを削除します。 既定のハンドラーでは、ツールバーを削除することであるかどうかを示す値を返します。|使用しません。|ポインター、`CMFCToolBar`削除されるオブジェクト。|ツールバーを 0 以外の場合は削除できません。それ以外の場合 0 を返します。|  
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` メイン フレーム ウィンドウをドキュメントの色を取得するには、このメッセージを送信します。|使用しません。|[入力、出力].ポインター、`CList<COLORREF, COLORREF>`オブジェクト。|0 を返します。|  
|AFX_WM_GETDRAGBOUNDS|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|ユーザーがリボンのリスト項目を強調表示したときに、メイン フレーム ウィンドウに送信されます。|強調表示されている項目のインデックス|ポインター `CMFCBaseRibbonElement`|使用しません。|  
|AFX_WM_ON_AFTER_SHELL_COMMAND|親に送信される`CMFCShellListCtrl`または`CMFCShellTreeCtrl`ユーザーのシェル コマンドの実行が終了したときを制御します。|ユーザーが実行したコマンドの ID|使用しません。|アプリケーションでは、このメッセージを処理する場合は 0 を返します。|  
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|フレームワークは、ポップアップ メニューを表示する前に、リボンの親にこのメッセージを送信します。 このメッセージを処理し、ポップアップ メニューをいつでも変更できます。|使用しません。|ポインター `CMFCBaseRibbonElement`|使用しません。|  
|AFX_WM_ON_CANCELTABMOVE|内部使用のみ。|該当なし。|該当なし。||  
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|フレームワークでは、ユーザーがアクティブのリボン コントロールの分類を変更したときに、このメッセージをメイン フレームに送信します。|使用しません。|ポインター、`CMFCRibbonBar`カテゴリが変更されています。|使用しません。|  
|AFX_WM_ON_CLOSEPOPUPWINDOW|フレームワークの所有者に通知するには、このメッセージを送信`CMFCDesktopAlertWnd`ウィンドウが閉じられようであります。|使用しません。|ポインター`CMFCDesktopAlertWnd`オブジェクト。|使用しません。|  
|AFX_WM_ON_DRAGCOMPLETE|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_ON_GET_TAB_TOOLTIP|タブ期間は、カスタム ツールヒントが有効になっている場合、タブのツールヒントを表示しようとしていますが、メイン フレーム ウィンドウに送信されます。|使用しません。|ポインター、`CMFCTabToolTipInfo`構造体。|使用しません。|  
|AFX_WM_ON_HSCROLL|サイズ変更可能なコントロール バー コントロールに送信されます。 通知を受信するには、このメッセージを処理`CMFCTabCtrl`タブ付きのウィジェットの水平スクロール バーのスクロール イベントの発生時のオブジェクトします。|下位ワードは、スクロール バーの値をユーザーを示すには要求のスクロールを指定します。  詳細については、このトピックで後に示す表を参照してください。|使用しません。|0 以外。|  
|AFX_WM_ON_MOVE_TAB|ユーザーの新しい位置にタブをドラッグしたときに、タブ付きウィンドウの親に送信されます。|元の位置で、タブの 0 から始まるインデックス。|[out]タブの新しい位置の 0 から始まるインデックス。|0 を返します。|  
|AFX_WM_ON_MOVETABCOMPLETE|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_ON_MOVETOTABGROUP|ユーザーでは、1 つのタブ付きグループ間 MDI 子ウィンドウを移動するときに、メイン フレーム ウィンドウに送信されます。|タブ付きウィンドウのハンドル (`CMFCTabCtrl`) から MDI 子ウィンドウが削除されました。|[out]タブ付きウィンドウのハンドル (`CMFCTabCtrl`) MDI 子ウィンドウに挿入されました。|無視されます。|  
|AFX_WM_ON_PRESS_CLOSE_BUTTON|親に送信される`CDockablePane`ユーザーがクリックしたとき、**閉じる**コントロール バーのキャプションのボタンをクリックします。|使用しません。|ユーザーがクリックされたドッキング可能ペインへのポインター、**閉じる**ボタンをクリックします。|`TRUE` 場合は、ウィンドウを閉じることができません。それ以外の場合は FALSE。|  
|AFX_WM_ON_RENAME_TAB|ユーザーが編集可能なタブを名前変更後に、タブ付きウィンドウの親に送信されます。|名前を変更したタブの 0 から始まるインデックス。|[out]新しいタブ名を表す文字列へのポインター。|アプリケーションは、このメッセージを処理する場合は 0 以外。フレームワークでの呼び出しを抑制する`CMFCBaseTabCtrl::SetTabLabel`です。  場合は、0 が返される`CMFCBaseTabCtrl::SetTabLabel`フレームワークによって呼び出されます。|  
|AFX_WM_ON_RIBBON_CUSTOMIZE|ユーザーがカスタマイズを開始するときに、親のフレームに送信されます。 独自のカスタマイズ ダイアログ ボックスを表示する場合は、このメッセージを処理します。|使用しません。|カスタマイズするリボン コントロールへのポインター。|以外の場合は、アプリケーションは、このメッセージを処理し、独自のカスタマイズ ダイアログ ボックスが表示されます。 アプリケーションでは、0 を返します、フレームワークにより、組み込みのカスタマイズ ダイアログ ボックスが表示されます。|  
|AFX_WM_ON_TABGROUPMOUSEMOVE|内部使用のみ。|該当なし。|該当なし。|該当なし。|  
|AFX_WM_POSTSETPREVIEWFRAME|ユーザーが印刷プレビュー モードを変更することをメイン フレームに通知されます。|`TRUE` 印刷プレビュー モードが設定されていることを示します。 `FALSE` 印刷プレビュー モードがになっていることを示します。|使用しません。|使用しません。|  
|AFX_WM_PROPERTY_CHANGED|プロパティ グリッド コントロールの所有者に送信 (`CMFCPropertyGridCtrl`)、ユーザーが選択されているプロパティの値を変更するときにします。|プロパティ リストのコントロール ID。|プロパティへのポインター (`CMFCPropertyGridProperty`) に変更します。|使用しません。|  
|AFX_WM_RESETCONTEXTMENU|ユーザーがカスタマイズ中に、コンテキスト メニューをリセットしたときに、メイン フレーム ウィンドウに送信されます。|コンテキスト メニューのリソース ID です。|現在のコンテキスト メニューへのポインター`CMFCPopupMenu`です。|使用しません。|  
|AFX_WM_RESETKEYBOARD|フレームワークは、ユーザーがカスタマイズ中にすべてのキーボード アクセラレータをリセットしたときに、メイン フレーム ウィンドウにこのメッセージを送信します。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_RESETMENU|フレームワークでは、このメッセージを送信 メニューの所有者 (フレーム ウィンドウ) に、ユーザーがカスタマイズ中に、アプリケーションのフレームのメニューをリセットすると|メニューの リソース id です。|使用しません。|使用しません。|  
|AFX_WM_RESETPROMPT|フレームワークは、ツールバーのツールバーから、ユーザーのリセット ダイアログ ボックスをカスタマイズするときに、このメッセージを送信します。 既定のハンドラーは、ユーザーがツールバーをリセットするかどうかを確認するメッセージ ボックスを表示します。|使用しません。|使用しません。|使用しません。|  
|AFX_WM_RESETTOOLBAR|A`CMFCToolBar`ツールバーを復元すると、元の状態は、リソースから読み込まれたオブジェクトはこのメッセージを送信します。 クラスが派生ツール バー ボタンを挿入するには、このメッセージを処理`CMFCToolbarButton`です。 詳細については、「`CMFCToolbarComboBoxButton`」を参照してください。|状態が復元されたツールバーのリソース ID です。|使用しません。|0 を返します。|  
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` オブジェクトは、ユーザーが標準のメニュー ボタンをクリックすると、その所有者にこのメッセージを送信します。 使用するたびにこのメッセージを処理`CMFCToolbarMenuButton`ユーザーがボタンをクリックしたときに、ポップアップ メニューを表示します。|メッセージを送信するボタンのコマンド ID。|カーソルの画面座標。 下位ワードは、x 座標を指定します。 上位ワードは、y 座標を指定します。|使用しません。|  
|AFX_WM_TOOLBARMENU|クライアントまたはウィンドウの非クライアント領域内にマウス ポインターが、ユーザーがマウスの右ボタンを離すと、メイン フレーム ウィンドウに送信されます。|使用しません。|マウス ポインターの画面座標。 下位ワードは、x 座標を指定します。 上位ワードは、y 座標を指定します。|アプリケーションは、このメッセージを処理する場合は 0 します。それ以外の場合、0 以外の値。|  
|AFX_WM_UPDATETOOLTIPS|ツールヒント コントロールを再作成することを示すために、ツールヒントのすべての所有者に送信されます。|このメッセージを処理するコントロールの型。 使用可能な値の一覧は、このトピックの後半の表を参照してください。|使用しません。|使用しません。|  
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` ユーザーがクリックしたときに、このメッセージを親フレームを送信、**ヘルプ** ボタン、またはをクリックしてヘルプ モードに入った、**ヘルプ**キャプション ボタンまたは F1 キーを押す。|使用しません。|インスタンスへのポインター`CMFCWindowsManagerDialog`です。|使用しません。|  
  
 次の表に、値の下位ワードを`lParam`AFX_WM_HSCROLL メソッドのパラメーター。  
  
|||  
|-|-|  
|[値]|説明|  
|SB_ENDSCROLL|ユーザーがスクロールを終了します。|  
|SB_LEFT|ユーザーは、左上にスクロールします。|  
|SB_RIGHT|ユーザーは、右下にスクロールします。|  
|SB_LINELEFT|ユーザーは、1 つの単位で左側をスクロールします。|  
|SB_LINERIGHT|ユーザーは、1 つの単位で右にスクロールします。|  
|SB_PAGELEFT|ユーザーは、左側のウィンドウの幅をスクロールします。|  
|SB_PAGERIGHT|ユーザー、ウィンドウの幅に右にスクロールします。|  
|SB_THUMBPOSITION|ユーザーがスクロール ボックス (つまみ) をドラッグし、マウス ボタンを解放します。 上位ワードは、ドラッグ操作の最後にスクロール ボックスの位置を示します。|  
|SB_THUMBTRACK|ユーザーがスクロール ボックスをドラッグします。 AFX_WM_ON_HSCROLL メッセージは、ユーザーがマウス ボタンを離すまでこの値を持つ繰り返し送信されます。 上位ワードは、スクロール ボックスをドラッグして位置を示します。|  
  
> [!NOTE]
>  上位ワード、`lParam`下位ワードが SB_THUMBPOSITION または SB_THUMBTRACK の場合、パラメーターをスクロール ボックスの現在の位置を指定します。 それ以外の場合、この単語は使用されません。  
  
 次の表に、フラグ値、 `lParam` AFX_WM_UPDATETOOLTIPS メッセージのパラメーター。  
  
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
|AFX_TOOLTIP_TYPE_ALL|0 xffff|  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
