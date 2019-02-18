---
title: ダイアログ ボックス (C++) のコントロール |Microsoft Docs
ms.date: 02/15/2019
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls [C++], about dialog box controls
- dialog box controls
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
ms.openlocfilehash: 6360491ebb4478ee4ce22115eced7ed672866565
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336515"
---
# <a name="controls-in-dialog-boxes-c"></a>ダイアログ ボックス (C++) のコントロール

コントロールを使用して、ダイアログ ボックスを追加することができます、[ダイアログ エディターのタブ](../windows/dialog-editor-tab-toolbox.md)で、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)、ダイアログ ボックスにドラッグしてコントロールを選択できます。 既定では、[ツールボックス] ウィンドウは、自動非表示に設定されます。 ダイアログ エディターが開いたとき、ソリューションの左余白のタブとして表示されます。 ただし、ピン留めできます、**ツールボックス**ウィンドウ位置をクリックして、**自動的に隠す**ウィンドウの右上隅のボタンをクリックします。 このウィンドウの動作を制御する方法の詳細については、次を参照してください。[ウィンドウ管理](/visualstudio/ide/customizing-window-layouts-in-visual-studio)します。

ダイアログ ボックスにコントロールを追加、既存のコントロールの位置を変更または 1 つのダイアログ ボックスから、コントロールを移動する最も簡単な方法では、ドラッグ アンド ドロップを使用します。 ダイアログ ボックスに、削除されるまで、コントロールの位置は点線で囲まれます。 ドラッグ アンド ドロップしてダイアログ ボックスにコントロールを追加すると、コントロールには、その種類のコントロールに適切な標準の高さが与えられます。

ガイドや、余白によって決定されます、最終的な配置 ダイアログ ボックスにコントロールを追加または位置を変更するときまたはレイアウト グリッドをオンにする必要があるかどうか。

キャプションなどのプロパティを変更するには、ダイアログ ボックスにコントロールを追加した後、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 複数のコントロールを選択し、そのプロパティをすべて一度に変更できます。

- [方法: 追加、編集、またはコントロールを削除](adding-editing-or-deleting-controls.md)

- [方法: コントロールを配置します。](../windows/arrangement-of-controls-on-dialog-boxes.md)

- [方法: アクセス制御と値を定義します。](../windows/defining-mnemonics-access-keys.md)

使用できる標準のコントロール、**ツールボックス**イベントは、既定値。

|コントロール名|既定のイベント|
|---|---|
|[ボタン コントロール](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[チェック ボックス コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[コンボ ボックス コントロール](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[コントロールを編集します。](../mfc/reference/cedit-class.md)|EN_CHANGE|
|グループ ボックス|(適用なし)|
|[リスト ボックス コントロール](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[ラジオ ボタン コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[スタティック テキスト コントロール](../mfc/reference/cstatic-class.md)|(適用なし)|
|[画像コントロール](../mfc/reference/cpictureholder-class.md)|(適用なし)|
|[リッチ エディット 2.0 コントロール](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[スクロール バー コントロール](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

使用しての詳細については、 **RichEdit 1.0** MFC でコントロールを参照してください[MFC での RichEdit 1.0 コントロールの使用](../windows/using-the-richedit-1-0-control-with-mfc.md)と[リッチ エディット コントロールの例](../mfc/rich-edit-control-examples.md)します。

[Windows コモン コントロール](../mfc/controls-mfc.md)で使用できる、**ツールボックス**アプリケーションで高度な機能を提供します。 それには以下が含まれます。

|コントロール名|既定のイベント|
|---|---|
|[スライダー コントロール](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[スピン コントロール](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[プログレス コントロール](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[ホット キー コントロール](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[リスト コントロール](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[ツリー コントロール](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[タブ コントロール](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[アニメーション コントロール](../mfc/using-an-animation-control.md)|ACN_START|
|[日時指定コントロール](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[月間予定表コントロールします。](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP アドレス コントロール](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[拡張コンボ ボックス コントロール](../mfc/creating-an-extended-combo-box-control.md)||
|カスタム コントロール|TTN_GETDISPINFO|

詳細については、次を参照してください。[コントロール クラス](../mfc/control-classes.md)、[ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)、および[スクロール バー スタイル](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)します。

## <a name="custom-controls"></a>カスタム コントロール

ダイアログ エディターを使用すると、既存の「カスタム」または"user"コントロールのダイアログ ボックスのテンプレート。

> [!NOTE]
> この意味でのカスタム コントロールでは、ActiveX コントロールと混同しないようにします。 ActiveX コントロールがカスタムの OLE コントロールとも呼ばれます。 また、Windows でオーナー描画コントロールでこれらのコントロールを混同しないでください。

この機能は、Windows によって提供されるもの以外のコントロールを使用することができます。 実行時に、コントロールは、ウィンドウ クラス (いないのと同じ C++ クラス) に関連付けられます。 同じタスクを実行する一般的な方法では、ダイアログ ボックスで、静的コントロールなどの任意のコントロールをインストールします。 実行時で、 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)機能、そのコントロールを削除し、独自のカスタム コントロールに置き換えます。

これは、以前の技術です。 今すぐ ActiveX コントロールまたは Windows のコモン コントロールのサブクラスを作成するほとんどの場合に推奨します。

これらのカスタム コントロール用に限定されます。

- ダイアログ ボックスで、場所を設定します。

- キャプションを入力します。

- (アプリケーション コードは、コントロールをこの名前に登録する必要があります)、コントロールの Windows クラスの名前を識別します。

- コントロールのスタイルを設定する 32 ビット 16 進値を入力します。

- 拡張スタイルを設定します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)<br/>
[コントロール](../mfc/controls-mfc.md)<br/>