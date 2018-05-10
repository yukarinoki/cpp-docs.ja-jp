---
title: コントロール クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- static display controls [MFC]
- control classes [MFC]
- buttons, MFC control classes
- controls [MFC], MFC control classes
- controls [MFC]
- list boxes [MFC], MFC control classes
- control classes [MFC], MFC
- text, controls for input [MFC]
- user input [MFC], MFC control classes
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffd7b3b7d2eb9db68fd61ac693c65d87b2ee62d7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="control-classes"></a>コントロール クラス
コントロール クラスには、さまざまな標準の Windows コントロールのツリー コントロールに静的テキスト コントロールの範囲がカプセル化します。 さらに、MFC には、いくつかの新しいコントロールのビットマップとコントロール バーのボタンが用意されています。  
  
 コントロールのクラス名の終わりに"**Ctrl**"Windows 95 および Windows NT version 3.51 の新しいです。  
  
## <a name="static-display-controls"></a>静的表示コントロール  
 [CStatic](../mfc/reference/cstatic-class.md)  
 静的表示ウィンドウです。 スタティック コントロールは、ラベル付け、ボックス、またはダイアログ ボックスまたはウィンドウの他のコントロールを個別に使用されます。 グラフィカル イメージではなくテキストまたはボックスを表示することもできます。  
  
## <a name="text-controls"></a>テキスト コントロール  
 [CEdit](../mfc/reference/cedit-class.md)  
 編集可能なテキスト コントロール ウィンドウの場合です。 編集コントロールを使用すると、ユーザーからのテキストの入力をそのまま使用します。  
  
 [関数](../mfc/reference/cipaddressctrl-class.md)  
 インターネット プロトコル (IP) アドレスを操作するためには、エディット ボックスをサポートします。  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 ユーザーを入力し、テキストを編集するをコントロールします。 内のカプセル化されたコントロールとは異なり`CEdit`、リッチ エディット コントロールには、文字と段落の書式設定および OLE オブジェクトがサポートしています。  
  
## <a name="controls-that-represent-numbers"></a>数値を表すコントロール  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 値または値のセットを選択し、移動、ユーザー、スライダーを持つコントロール。  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 矢印ボタンの組み合わせ、ユーザーは、値を増減するをクリックできます。  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 塗りつぶされて左から右に操作の進行状況を示す四角形が表示されます。  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 スクロール バー コントロール ウィンドウ。 クラスは、ダイアログ ボックスまたはウィンドウで、ユーザーが範囲内での位置を指定のコントロールとして使用するためのスクロール バーの機能を提供します。  
  
## <a name="buttons"></a>ボタン  
 [CButton](../mfc/reference/cbutton-class.md)  
 ボタン コントロール ウィンドウ。 クラスは、プッシュ ボタン、チェック ボックスをオンまたはダイアログ ボックスまたはウィンドウのオプション ボタンのプログラム インターフェイスを提供します。  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 テキスト キャプションではなくビットマップのボタンをクリックします。  
  
## <a name="lists"></a>表示内容  
 [CListBox](../mfc/reference/clistbox-class.md)  
 リスト ボックス コントロール ウィンドウ。 リスト ボックスには、ユーザーは表示したり、選択できるアイテムの一覧が表示されます。  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Windows のリスト ボックスの機能を提供します。リスト ボックス内で、ファイル名と文字列リテラルなどのリスト ボックス項目を移動することができます。 この機能を持つリスト ボックスは、役立ちます。 のアルファベット以外の順序でアイテムのリストなどのパス名またはファイルをプロジェクトに含めます。  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 コンボ ボックス コントロール ウィンドウ。 コンボ ボックスは、エディット コントロールとリスト ボックスで構成されます。  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 ユーザーを確認したり、オフに、各アイテムの横のチェック ボックスを使用して項目の一覧を表示します。  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 アイコンとラベルをファイル エクスプ ローラーの右側のウィンドウと同様の方法で構成される各項目のコレクションを表示します。  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 ファイル エクスプ ローラーの左側のウィンドウと同様の方法で配置されたラベルとアイコンの階層リストを表示します。  
  
## <a name="toolbars-and-status-bars"></a>ツールバーとステータス バー  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows ツール バー コモン コントロールの機能が用意されています。 ほとんどの MFC プログラムを使用して[CToolBar](../mfc/reference/ctoolbar-class.md)このクラスの代わりにします。  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 水平方向のウィンドウは、通常、ペイン、アプリケーションが状態情報を表示できますに分かれています。 ほとんどの MFC プログラムを使用して[CStatusBar](../mfc/reference/cstatusbar-class.md)このクラスの代わりにします。  
  
## <a name="miscellaneous-controls"></a>その他のコントロール  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 単純なビデオ クリップを表示します。  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 アプリケーションでツールの用途を説明するテキストを 1 行を表示する小さなポップアップ ウィンドウです。  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 拡張の編集コントロール、または、ユーザーが特定の日付または時刻の値を選択できる単純なカレンダー インターフェイスのコントロールのいずれかをサポートしています。  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 列のタイトルまたはラベルを表示します。  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 ユーザーが日付を選択できる単純なカレンダー インターフェイス コントロールをサポートしています。  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 ユーザーがクリックして、ノートの仕切りに似ていますタブ コントロールです。  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 作成、ホット キーの組み合わせを押すと、アクションをすばやく実行することができます。  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 テキストを表示され、ユーザーが埋め込みリンクをクリックしたときに、適切なアプリケーションを起動します。  
  
 [関数](../mfc/reference/chtmleditctrl-class.md)  
 MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。  
  
## <a name="related-classes"></a>関連するクラス  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Windows イメージ リストの機能を提供します。 イメージ リストは、ツリー コントロールとリスト コントロールで使用されます。 格納し、同じサイズのビットマップのセットをアーカイブも使用できます。  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows のコントロールに関連付けられているすべてのビューの基底クラス。 コントロールに基づくビューは次のとおりです。  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 標準の Windows を含むビューは、コントロールを編集します。  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 豊富な Windows を含むビューは、コントロールを編集します。  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows のリスト コントロールを含むビュー。  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows のツリー コントロールを含むビュー。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

