---
description: '詳細情報: コントロールクラス'
title: コントロール クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
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
ms.openlocfilehash: eb0bee6d865867a052b5f49408bdaa1b70da343f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310123"
---
# <a name="control-classes"></a>コントロール クラス

コントロールクラスは、静的なテキストコントロールからツリーコントロールまで、さまざまな標準の Windows コントロールをカプセル化します。 さらに、MFC には、ビットマップやコントロールバーを含むボタンなど、いくつかの新しいコントロールが用意されています。

クラス名が "**Ctrl**" で終わるコントロールは、windows 95 および windows NT version 3.51 で新しく追加されました。

## <a name="static-display-controls"></a>静的表示コントロール

[CStatic](reference/cstatic-class.md)<br/>
静的表示ウィンドウ。 静的コントロールは、ダイアログボックスまたはウィンドウ内の他のコントロールのラベル付け、ボックス、または分離に使用されます。 また、テキストやボックスではなく、グラフィカルな画像が表示される場合もあります。

## <a name="text-controls"></a>テキストコントロール

[CEdit](reference/cedit-class.md)<br/>
編集可能なテキストコントロールウィンドウ。 編集コントロールは、ユーザーからのテキスト入力を受け入れるために使用されます。

[CIPAddressCtrl](reference/cipaddressctrl-class.md)<br/>
では、インターネットプロトコル (IP) アドレスを操作するためのエディットボックスがサポートされています。

[CRichEditCtrl](reference/cricheditctrl-class.md)<br/>
ユーザーがテキストを入力および編集できるコントロール。 でカプセル化されたコントロールとは異なり `CEdit` 、リッチエディットコントロールでは、文字および段落の書式設定と OLE オブジェクトがサポートされます。

## <a name="controls-that-represent-numbers"></a>数値を表すコントロール

[CSliderCtrl](reference/csliderctrl-class.md)<br/>
スライダーを含むコントロール。ユーザーは、値または値のセットを選択するために移動します。

[CSpinButtonCtrl](reference/cspinbuttonctrl-class.md)<br/>
ユーザーがクリックして値を増減できる矢印ボタンのペア。

[CProgressCtrl](reference/cprogressctrl-class.md)<br/>
操作の進行状況を示すために左から右に徐々に入力された四角形を表示します。

[CScrollBar](reference/cscrollbar-class.md)<br/>
スクロールバーコントロールウィンドウ。 クラスは、ユーザーが範囲内の位置を指定できるようにするために、ダイアログボックスまたはウィンドウでコントロールとして使用するスクロールバーの機能を提供します。

## <a name="buttons"></a>ボタン

[CButton](reference/cbutton-class.md)<br/>
ボタンコントロールウィンドウ。 クラスは、ダイアログボックスまたはウィンドウのプッシュボタン、チェックボックス、またはオプションボタンのためのプログラムインターフェイスを提供します。

[CBitmapButton](reference/cbitmapbutton-class.md)<br/>
テキストキャプションではなくビットマップを持つボタン。

## <a name="lists"></a>表示内容

[CListBox](reference/clistbox-class.md)<br/>
リストボックスコントロールウィンドウ。 リストボックスには、ユーザーが表示および選択できる項目の一覧が表示されます。

[CDragListBox](reference/cdraglistbox-class.md)<br/>
Windows のリストボックスの機能を提供します。リストボックス内で、ファイル名や文字列リテラルなどのリストボックス項目を移動できるようにします。 この機能を持つリストボックスは、項目リストがアルファベット以外の順序で表示される場合に便利です (パス名やプロジェクト内のファイルなど)。

[CComboBox](reference/ccombobox-class.md)<br/>
コンボボックスコントロールウィンドウ。 コンボボックスは、エディットコントロールとリストボックスで構成されます。

[CComboBoxEx](reference/ccomboboxex-class.md)<br/>
イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。

[CCheckListBox](reference/cchecklistbox-class.md)<br/>
各項目の横にあるチェックボックスをオンまたはオフにして、項目の一覧を表示します。

[CListCtrl](reference/clistctrl-class.md)<br/>
ファイルエクスプローラーの右側のウィンドウと同様の方法で、項目のコレクションを表示します。各項目はアイコンとラベルで構成されています。

[CTreeCtrl](reference/ctreectrl-class.md)<br/>
ファイルエクスプローラーの左側のウィンドウと同様の方法で配置されたアイコンとラベルの階層リストを表示します。

## <a name="toolbars-and-status-bars"></a>ツールバーとステータスバー

[CToolBarCtrl](reference/ctoolbarctrl-class.md)<br/>
Windows ツール バー コモン コントロールの機能が用意されています。 ほとんどの MFC プログラムは、このクラスではなく、 [CToolBar](reference/ctoolbar-class.md) を使用します。

[CStatusBarCtrl](reference/cstatusbarctrl-class.md)<br/>
水平方向のウィンドウ。通常はウィンドウに分割され、アプリケーションで状態情報を表示できます。 ほとんどの MFC プログラムは、このクラスではなく [CStatusBar](reference/cstatusbar-class.md) を使用します。

## <a name="miscellaneous-controls"></a>その他のコントロール

[CAnimateCtrl](reference/canimatectrl-class.md)<br/>
単純なビデオクリップを表示します。

[CToolTipCtrl](reference/ctooltipctrl-class.md)<br/>
アプリケーション内のツールの目的を説明する1行のテキストを表示する小さなポップアップウィンドウ。

[CDateTimeCtrl](reference/cdatetimectrl-class.md)<br/>
拡張エディットコントロール、またはユーザーが特定の日付または時刻の値を選択できる単純な calendar インターフェイスコントロールをサポートします。

[CHeaderCtrl](reference/cheaderctrl-class.md)<br/>
列のタイトルまたはラベルを表示します。

[CMonthCalCtrl](reference/cmonthcalctrl-class.md)<br/>
ユーザーが日付を選択できる単純な calendar interface コントロールをサポートします。

[CTabCtrl](reference/ctabctrl-class.md)<br/>
ユーザーがクリックできるタブを持つコントロール。 notebook の区分線に似ています。

[CHotKeyCtrl](reference/chotkeyctrl-class.md)<br/>
ユーザーがホットキーの組み合わせを作成できるようにします。ユーザーは、このキーを押して、操作をすばやく実行できます。

[CLinkCtrl](reference/clinkctrl-class.md)<br/>
マークアップされたテキストを表示し、ユーザーが埋め込みリンクをクリックしたときに適切なアプリケーションを起動します。

[CHtmlEditCtrl](reference/chtmleditctrl-class.md)<br/>
MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。

## <a name="related-classes"></a>関連クラス

[CImageList](reference/cimagelist-class.md)<br/>
Windows イメージリストの機能を提供します。 イメージリストは、リストコントロールおよびツリーコントロールで使用されます。 また、同じサイズのビットマップのセットを格納してアーカイブするために使用することもできます。

[CCtrlView](reference/cctrlview-class.md)<br/>
Windows コントロールに関連付けられているすべてのビューの基本クラス。 以下では、コントロールに基づくビューについて説明します。

[CEditView](reference/ceditview-class.md)<br/>
Windows 標準の編集コントロールを含むビュー。

[CRichEditView](reference/cricheditview-class.md)<br/>
Windows リッチエディットコントロールを含むビュー。

[CListView](reference/clistview-class.md)<br/>
Windows リストコントロールを含むビュー。

[CTreeView](reference/ctreeview-class.md)<br/>
Windows のツリーコントロールを含むビュー。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
