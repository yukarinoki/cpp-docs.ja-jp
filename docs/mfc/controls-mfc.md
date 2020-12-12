---
description: '詳細情報: コントロール (MFC)'
title: コントロール (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
ms.openlocfilehash: 94406928741eecd00794dbde230effe4d89ab3f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310136"
---
# <a name="controls-mfc"></a>コントロール (MFC)

コントロールは、データを入力または操作するときにユーザーが取り扱うオブジェクトです。 通常は、ダイアログ ボックスまたはツール バー上に表示されます。 ここでは、主な 3 種類のコントロールについて説明します。

- オーナー描画コントロールなどの Windows コモン コントロール

- ActiveX コントロール

- MFC (Microsoft Foundation Class) ライブラリで提供される、その他のコントロール クラス

## <a name="windows-common-controls"></a>Windows コモン コントロール

Windows オペレーティング システムでは、多数の Windows コモン コントロールが提供されています。 これらのコントロール オブジェクトはコードから操作できます。また、Visual C++ ダイアログ エディターを使用して、コントロール オブジェクトをダイアログ ボックスに追加できます。 MFC (Microsoft Foundation Class) ライブラリでは、表「 [Windows コモン コントロールと MFC クラス](#_core_windows_common_controls_and_mfc_classes)」に記述されているように、各コントロールをカプセル化するためのクラスが提供されています。 (表内の一部の項目は、詳細を説明するトピックに関連付けられています)。 トピックに関連付けられていないコントロールについては、MFC クラスに関するドキュメントを参照してください。

[CWnd](reference/cwnd-class.md) クラスは、コントロール クラスをすべて含む、すべてのウィンドウ クラスの基底クラスです。

## <a name="activex-controls"></a>ActiveX コントロール

ActiveX コントロールは、以前は OLE コントロールと呼ばれていたもので、Windows アプリケーション、または WWW (World Wide Web) の HTML ページで使用できます。 詳細については、「 [MFC ActiveX コントロール](mfc-activex-controls.md)」を参照してください。

## <a name="other-mfc-control-classes"></a>その他の MFC コントロール クラス

すべての Windows コモン コントロールをカプセル化するクラスと、ユーザー独自の (または他のアプリケーションにより提供された) ActiveX コントロールのプログラミングをサポートするクラスに加えて、MFC では以下のコントロール クラスを独自に提供します。

- [CBitmapButton](reference/cbitmapbutton-class.md)

- [CCheckListBox](reference/cchecklistbox-class.md)

- [CDragListBox](reference/cdraglistbox-class.md)

## <a name="finding-information-about-windows-common-controls"></a><a name="_core_finding_information_about_windows_common_controls"></a> Windows コモンコントロールに関する情報の入手

次の表では、MFC ラッパー クラスを含む Windows コモン コントロールについて簡単に説明します。

### <a name="windows-common-controls-and-mfc-classes"></a><a name="_core_windows_common_controls_and_mfc_classes"></a> Windows コモンコントロールと MFC クラス

|コントロール|MFC クラス|説明|Windows 95 の新方法|
|-------------|---------------|-----------------|------------------------|
|[animation](using-canimatectrl.md)|[CAnimateCtrl](reference/canimatectrl-class.md)|AVI ビデオ クリップのフレームを連続的に表示します。|はい|
|ボタン|[CButton](reference/cbutton-class.md)|アクションを発生させるプッシュ ボタン。チェック ボックス、オプション ボタン、およびグループ ボックスにも使用します。|いいえ|
|コンボ ボックス|[CComboBox](reference/ccombobox-class.md)|エディット ボックスとリスト ボックスを組み合わせたものです。|いいえ|
|[日時指定](using-cdatetimectrl.md)|[CDateTimeCtrl](reference/cdatetimectrl-class.md)|ユーザーが特定の日付または時刻の値を選択できます。|はい|
|エディット ボックス|[CEdit](reference/cedit-class.md)|テキスト入力用のボックスです。|いいえ|
|[拡張コンボ ボックス](using-ccomboboxex.md)|[CComboBoxEx](reference/ccomboboxex-class.md)|イメージを表示できるコンボ ボックス コントロールです。|はい|
|[項目](using-cheaderctrl.md)|[CHeaderCtrl](reference/cheaderctrl-class.md)|テキストの列の上に表示されるボタンで、テキストの表示幅を制御します。|はい|
|[ホットキー](using-chotkeyctrl.md)|[CHotKeyCtrl](reference/chotkeyctrl-class.md)|アクションをすばやく実行するための "ホット キー" を作成できるウィンドウです。|はい|
|[イメージ リスト。](using-cimagelist.md)|[CImageList](reference/cimagelist-class.md)|多数のアイコンまたはビットマップの管理に使用するイメージのコレクションです。イメージ リストは実際にはコントロールではなく、他のコントロールで使用されるリストをサポートします。|はい|
|[list](using-clistctrl.md)|[CListCtrl](reference/clistctrl-class.md)|アイコンと共にテキストのリストを表示するウィンドウです。|はい|
|リスト ボックス|[CListBox](reference/clistbox-class.md)|文字列のリストを格納するボックスです。|いいえ|
|[月間予定表](using-cmonthcalctrl.md)|[CMonthCalCtrl](reference/cmonthcalctrl-class.md)|日付情報を表示するコントロールです。|はい|
|[進行状況](using-cprogressctrl.md)|[CProgressCtrl](reference/cprogressctrl-class.md)|時間のかかる処理を実行する場合に、その進行状況を示すウィンドウです。|はい|
|[rebar](using-crebarctrl.md)|[CRebarCtrl](reference/crebarctrl-class.md)|子ウィンドウをコントロールとして追加できるツール バーです。|はい|
|[リッチ エディット](using-cricheditctrl.md)|[CRichEditCtrl](reference/cricheditctrl-class.md)|ユーザーが文字書式および段落書式を設定して編集できるウィンドウです (「 [リッチ エディット コントロールに関連するクラス](classes-related-to-rich-edit-controls.md)」を参照)。|はい|
|スクロール バー|[CScrollBar](reference/cscrollbar-class.md)|ウィンドウ上ではなくダイアログ ボックス内のコントロールとして使用されるスクロール バーです。|いいえ|
|[slider](using-csliderctrl.md)|[CSliderCtrl](reference/csliderctrl-class.md)|オプションで軸目盛りを表示できるスライダー コントロールが配置されたウィンドウです。|はい|
|[スピン ボタン](using-cspinbuttonctrl.md)|[CSpinButtonCtrl](reference/cspinbuttonctrl-class.md)|ユーザーが値の増減をクリック操作で指定できる矢印ボタンです。増加用と減少用がペアになっています。|はい|
|静的テキスト|[CStatic](reference/cstatic-class.md)|他のコントロールのラベルに使用するテキストです。|いいえ|
|[ステータスバー](using-cstatusbarctrl.md)|[CStatusBarCtrl](reference/cstatusbarctrl-class.md)|ステータス情報を表示するためのウィンドウです。MFC クラスの `CStatusBar`に似ています。|はい|
|[] タブ](using-ctabctrl.md)|[CTabCtrl](reference/ctabctrl-class.md)|ノートの仕切りのような役割を果たします。"タブ ダイアログ ボックス" またはプロパティ シートで使用します。|はい|
|[toolbar](using-ctoolbarctrl.md)|[CToolBarCtrl](reference/ctoolbarctrl-class.md)|コマンド生成ボタンを持つウィンドウです。MFC クラスの `CToolBar`に似ています。|はい|
|[ツールヒント](using-ctooltipctrl.md)|[CToolTipCtrl](reference/ctooltipctrl-class.md)|ツール バー ボタンなどのツールの用途の説明を表示する小さなポップアップ ウィンドウです。|はい|
|[tree](using-ctreectrl.md)|[CTreeCtrl](reference/ctreectrl-class.md)|項目を階層化されたリストとして表示するウィンドウです。|はい|

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- 各コントロールへのリンクについては、上記の「 [Windows コモン コントロールと MFC クラス](#_core_windows_common_controls_and_mfc_classes) 」を参照してください。

- [コントロールの作成方法と使い方](making-and-using-controls.md)

- [ダイアログエディターを使用したコントロールの追加](using-the-dialog-editor-to-add-controls.md)

- [手動でコントロールを追加する方法](adding-controls-by-hand.md)

- [MFC コントロール クラスからのコントロール クラスの派生](deriving-controls-from-a-standard-control.md)

- [子ウィンドウとしてのコモン コントロールの使い方](using-a-common-control-as-a-child-window.md)

- [コモン コントロールからの通知の受信](receiving-notification-from-common-controls.md)

- ["Add common controls to a dialog box (ダイアログ ボックスへのコントロールの追加)"](using-common-controls-in-a-dialog-box.md)。

- [Windows 標準コントロールからのコントロールの派生](deriving-controls-from-a-standard-control.md)

- [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](type-safe-access-to-controls-in-a-dialog-box.md)

- [コモン コントロールからの通知の受信](receiving-notification-from-common-controls.md)

- [サンプル](common-control-sample-list.md)

Windows SDK の Windows コモンコントロールの詳細については、「 [コモンコントロール](/windows/win32/Controls/common-controls-intro)」を参照してください。

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)<br/>
[ダイアログエディター](../windows/dialog-editor.md)
