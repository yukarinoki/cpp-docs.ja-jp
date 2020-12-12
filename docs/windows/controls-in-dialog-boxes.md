---
description: '詳細情報: ダイアログボックスコントロール (C++)'
title: ダイアログボックスコントロール (C++) |Microsoft Docs
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
ms.openlocfilehash: e68547ebd550797d4ad195c6bef4c3f2a71e769e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327149"
---
# <a name="dialog-box-controls-c"></a>ダイアログボックスコントロール (C++)

コントロールをダイアログボックスに追加するには、[[ツールボックス] ウィンドウ](/visualstudio/ide/reference/toolbox)の [**ダイアログエディター** ] タブを使用します。このタブでは、必要なコントロールを選択してダイアログボックスにドラッグできます。 既定では、[ **ツールボックス** ] ウィンドウは [自動的に隠す] に設定されています。 **ダイアログエディター** が開いているときに、ソリューションの左余白にタブとして表示されます。 ただし、ウィンドウの右上隅にある [**自動的に隠す**] ボタンを選択して、**ツールボックス** ウィンドウを位置にピン留めすることができます。 このウィンドウの動作を制御する方法の詳細については、「 [ウィンドウ管理](/visualstudio/ide/customizing-window-layouts-in-visual-studio)」を参照してください。

ダイアログボックスにコントロールを追加したり、既存のコントロールの位置を変更したり、ダイアログボックスから別のダイアログボックスにコントロールを移動したりする最も簡単な方法は、ドラッグアンドドロップを使用する方法です。 コントロールの位置は、ダイアログボックスにドロップされるまで点線で囲まれています。 ドラッグアンドドロップメソッドを使用してコントロールをダイアログボックスに追加すると、コントロールには、そのコントロールの種類に適した標準の高さが与えられます。

コントロールをダイアログボックスに追加したり、コントロールの位置を変更したりすると、その最終的な配置は、ガイドや余白によって決まります。または、レイアウトグリッドが有効になっているかどうかによって決まります。

ダイアログボックスにコントロールを追加したら、[ [プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)でキャプションなどのプロパティを変更できます。 複数のコントロールを選択し、それらのプロパティをすべて一度に変更することもできます。

**ダイアログエディター** の詳細については、「[コントロールを追加、編集、または削除](adding-editing-or-deleting-controls.md)する方法」、「[レイアウトコントロール](../windows/arrangement-of-controls-on-dialog-boxes.md)」、および「[コントロールのアクセスと値の定義](../windows/defining-mnemonics-access-keys.md)」を参照してください。

コントロールとダイアログの詳細については、「 [コントロールクラス](../mfc/control-classes.md)」、「 [ダイアログボックスのクラス](../mfc/dialog-box-classes.md)」、および「 [スクロールバーのスタイル](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)」を参照してください。

既定のイベントを使用して **ツールボックス** で使用できる標準コントロールは次のとおりです。

|コントロール名|既定のイベント|
|---|---|
|[ボタンコントロール](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[チェック ボックス コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[コンボ ボックス コントロール](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[編集コントロール](../mfc/reference/cedit-class.md)|EN_CHANGE|
|グループ ボックス|(該当なし)|
|[リストボックスコントロール](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[ラジオ ボタン コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[スタティック テキスト コントロール](../mfc/reference/cstatic-class.md)|(該当なし)|
|[画像コントロール](../mfc/reference/cpictureholder-class.md)|(該当なし)|
|[リッチ エディット 2.0 コントロール](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[スクロール バー コントロール](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

> [!NOTE]
> MFC での **richedit 1.0** コントロールの使用方法の詳細については、「mfc での [richedit 1.0 コントロールの使用](./adding-editing-or-deleting-controls.md) 」および「 [リッチエディットコントロールの例](../mfc/rich-edit-control-examples.md)」を参照してください。

**ツールボックス** で使用できる [Windows コモンコントロール](../mfc/controls-mfc.md)は、次のような機能を提供します。

|コントロール名|既定のイベント|
|---|---|
|[Slider コントロール](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[スピン コントロール](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[プログレス コントロール](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[ホット キー コントロール](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[リスト コントロール](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[ツリー コントロール](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[タブ コントロール](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[アニメーション コントロール](../mfc/using-an-animation-control.md)|ACN_START|
|[日付と時刻の選択コントロール](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[月間予定表コントロール](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP アドレス制御](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[拡張コンボ ボックス コントロール](../mfc/creating-an-extended-combo-box-control.md)||
|カスタム コントロール|TTN_GETDISPINFO|

## <a name="custom-controls"></a>カスタム コントロール

ダイアログ **エディター** では、ダイアログボックステンプレートで既存のカスタムコントロールまたはユーザーコントロールを使用できます。

> [!NOTE]
> この意味でのカスタムコントロールは、ActiveX コントロールと混同しないようにしてください。 ActiveX コントロールは、OLE カスタムコントロールとも呼ばれます。 また、これらのコントロールは、Windows のオーナー描画コントロールと混同しないようにしてください。

この機能は、Windows によって提供されるコントロール以外のコントロールを使用できるようにするためのものです。 実行時に、コントロールはウィンドウクラスに関連付けられます (C++ クラスとは異なります)。 同じタスクを実行する一般的な方法として、ダイアログボックスに静的コントロールなどのコントロールをインストールする方法があります。 次に、実行時に、 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 関数でそのコントロールを削除し、独自のカスタムコントロールに置き換えます。

> [!NOTE]
> これは以前の手法です。 現在、ほとんどの場合、ActiveX コントロールを記述するか、Windows コモンコントロールをサブクラス化することをお勧めします。

これらのカスタムコントロールでは、次のことに制限されています。

- ダイアログボックス内の場所を設定します。

- キャプションを入力します。

- アプリケーションコードがこの名前によってコントロールを登録する必要があるため、コントロールの Windows クラスの名前を識別します。

- コントロールのスタイルを設定する32ビットの16進値を入力します。

- 拡張スタイルを設定しています。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログエディター](../windows/dialog-editor.md)

<!--
[Adding Event Handlers for Dialog Box Controls](./adding-editing-or-deleting-controls.md)<br/>
[Dialog Box Controls and Variable Types](../ide/adding-a-member-variable-visual-cpp.md#dialog-box-controls-and-variable-types)<br/>
[Controls](../mfc/controls-mfc.md)<br/>-->
