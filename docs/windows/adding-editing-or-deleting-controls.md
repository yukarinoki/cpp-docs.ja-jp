---
title: コントロールの追加、編集、または削除
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Dialog Editor [C++], creating controls
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
- dialog box controls [C++], deleting
- controls [C++], deleting
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: b4edb5b7a51e4f6d368759ebc2e05a1cc585f19a
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742753"
---
# <a name="adding-editing-or-deleting-controls"></a>コントロールの追加、編集、または削除

使用して、**ダイアログ**エディター、追加できますが、サイズを変更、編集、およびダイアログ ボックスのコントロールを削除します。 をその ID などのコントロールのプロパティを編集することもできるかどうか、最初に表示される実行時にします。

**ダイアログ エディター**タブに表示されます、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)作業するとき、**ダイアログ**エディター。 カスタマイズすることも、**ツールボックス**ウィンドウを簡単に使用します。 詳細については、次を参照してください。[ツールボックスを使用して](/visualstudio/ide/using-the-toolbox)と[表示または非表示のツールボックス ウィンドウ](showing-or-hiding-the-dialog-editor-toolbar.md)します。

ショートカット メニューを使用することができます、**ダイアログ**エディターにすばやく追加するには、ActiveX コントロールのダイアログ ボックスが登録されているし、ActiveX コントロールを追加することができます、**ツールボックス**すばやくアクセスできます。

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
|[カスタム コントロール](custom-controls-in-the-dialog-editor.md)|TTN_GETDISPINFO|

詳細については、次を参照してください。[コントロール クラス](../mfc/control-classes.md)、[ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)、および[スクロール バー スタイル](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)します。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="to-add-a-control"></a>コントロールを追加するには

新しいダイアログ ボックスにコントロールを追加するからコントロールをドラッグ、**ツールボックス** ダイアログ ボックスを作成します。 次いでコントロールの移動、またはサイズと形状の変更ができます。

ダイアログ ボックスにカスタム コントロールを追加するには選択して、**カスタム コントロール**アイコン、**ツールボックス**ダイアログ ボックスにドラッグするとします。 追加する、 **Syslink**を制御し、カスタム コントロールを追加、変更、コントロールの**クラス**プロパティを**Syslink**します。 この操作は、プロパティが更新され、表示により、 **Syslink**プロパティを制御します。 MFC ラッパー クラスについては、次を参照してください。 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)します。

### <a name="to-add-a-control-to-a-dialog-box"></a>ダイアログ ボックスにコントロールを追加するには

1. ダイアログ ボックスのタブ付きウィンドウがエディター フレーム内の現在のドキュメントであることを確認します。 ダイアログ ボックスが現在のドキュメントでない場合は表示されません、**ダイアログ エディターのタブ**で、**ツールボックス**します。

1. **ダイアログ エディター**のタブ、**ツールボックス**ウィンドウで、目的のコントロールを選択します。

   コントロールを配置する場所 ダイアログ ボックスを選択します。 選択したコントロールが表示されます。

   \- または -

   ドラッグ アンド ドロップのコントロール、**ツールボックス**ウィンドウ、ダイアログ ボックス上の場所にします。

   \- または -

   コントロールをダブルクリック、**ツールボックス**ウィンドウ (ダイアログ ボックスに表示) したい場所にコントロールを再配置します。

### <a name="to-add-multiple-controls"></a>複数のコントロールを追加するには

1. 押しながら、 **Ctrl**キーでコントロールを選び、**ツールボックス**ウィンドウ。

1. リリース、 **Ctrl**キーを何度でも、特定のコントロールを追加すると、ダイアログ ボックスを選択します。

1. キーを押して**Esc**コントロールの配置を停止します。

### <a name="to-size-a-control-while-you-add-it"></a>追加するコントロールのサイズ

1. コントロールを選び、**ツールボックス**ウィンドウ。

1. ダイアログ ボックスで、新しいコントロールの左上隅となる (これに十字が表示されます)、カーソルを置きます。

1. 選択し、ダイアログ ボックスで、コントロールの左上隅に固定するマウス ボタンを押したまま、目的のサイズになるまで、右、下にカーソルをドラッグします。

   > [!NOTE]
   > 実際に描画するコントロールの四隅のいずれかを固定できます。 この手順では、例として、左上隅にあるを使用します。

1. マウスのボタンを離します。 指定したサイズでダイアログ ボックスにコントロールが配置されます。

   > [!TIP]
   > コントロールのサイズを変更するには、コントロールの境界線にサイズ変更ハンドルを移動することによって、ダイアログ ボックスの上にドロップするとします。 詳細については、次を参照してください。[個々 のコントロールをサイズ変更](../windows/sizing-individual-controls.md)します。

### <a name="to-add-an-activex-control"></a>ActiveX コントロールを追加するには

Visual Studio では、ActiveX コントロールをダイアログ ボックスに挿入することができます。 詳細については、次を参照してください。 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)と[ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)します。

**ActiveX コントロールの挿入** ダイアログ ボックスでは、使用中に、ダイアログ ボックスに ActiveX コントロールを挿入することができます、[ダイアログ エディター](../windows/dialog-editor.md)します。 このダイアログ ボックスには、次のプロパティが含まれています。

|プロパティ|説明|
|---|---|
|**ActiveX コントロール**|Active X コントロールの一覧が表示されます。 このダイアログ ボックスからコントロールを挿入すると、ラッパー クラスを生成しません。 ラッパー クラスを必要がある場合を使用して、[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)を作成する (詳細については、次を参照してください。[クラスの追加](../ide/adding-a-class-visual-cpp.md))。 このダイアログ ボックスで、Active X コントロールが表示されない場合は、ベンダーの指示に従ってコントロールをインストールしてみてください。|
|**パス**|ActiveX コントロールが掲載されているファイルを表示します。|

#### <a name="to-see-the-activex-controls-available"></a>使用できる ActiveX コントロールを表示するには

1. ダイアログ エディターでダイアログ ボックスを開きます。

1. ダイアログ ボックスの本文内を右クリックします。

1. ショートカット メニューでは、次のように選択します。 **ActiveX コントロールの挿入**します。

   **ActiveX コントロールの挿入**システム上のすべての ActiveX コントロールを示すダイアログ ボックスが表示されます。 ダイアログ ボックスの下部には、ActiveX コントロール ファイルへのパスが表示されます。

#### <a name="to-add-an-activex-control-to-a-dialog-box"></a>ダイアログ ボックスに ActiveX コントロールを追加するには

1. **ActiveX コントロールの挿入** ダイアログ ボックスで、ダイアログ ボックスに追加し、選択するコントロールを選択します。 **OK**します。

   コントロールがダイアログ ボックスに表示されます。このダイアログ ボックスで、他のコントロールでするのと同じように、コントロールの編集またはそのハンドラーの作成を行います。

   > [!NOTE]
   > ActiveX コントロールを追加することができます、**ツールボックス**ウィンドウを簡単にアクセスします。

   > [!CAUTION]
   > システム上の ActiveX コントロールの中には、配布が法的に許可されていないものもあります。 コントロールをインストールしたソフトウェアのライセンス契約を参照するか、ソフトウェア会社に問い合わせてください。

## <a name="to-edit-a-control"></a>コントロールを編集するには

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>コントロールまたはコントロールのプロパティを編集するには

1. ダイアログ ボックスで、変更するコントロールを選択します。

   > [!NOTE]
   > 複数のコントロールを選択した場合は、選択したコントロールの共通プロパティのみを編集できます。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)コントロールのプロパティを変更します。

   > [!NOTE]
   > 設定すると、**ビットマップ**ボタン、オプション ボタン、またはチェック ボックス コントロールと同じプロパティを**True**BS_BITMAP の実装は、コントロールのスタイル。 詳細については、次を参照してください。[ボタンのスタイル](../mfc/reference/styles-used-by-mfc.md#button-styles)します。 コントロールとビットマップの関連付けの例は、次を参照してください。 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)します。 は、ビットマップは、コントロールに表示されません、**ダイアログ**リソース エディター。

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>コントロールのプロパティの変更を元に戻す

1. コントロールにフォーカスがあるかどうかを確認、**ダイアログ**エディター。

1. 選択**を元に戻す**から、**編集**メニュー (コントロールにフォーカスがない場合、**を元に戻す**コマンドは使用できません)。

### <a name="to-edit-properties-for-an-activex-control"></a>ActiveX コントロールのプロパティを編集するには

独立系ベンダーによって提供される ActiveX コントロールは、独自のプロパティと特性が搭載可能性があります。 ActiveX コントロールのプロパティが表示されます、**プロパティ**ウィンドウ。 ActiveX コントロールの作成者によって作成されたすべてのプロパティ ページを表示することも、**プロパティ ページ** ダイアログ ボックス (表示する、**プロパティ ページ**特定の ActiveX コントロールをクリックして、 **プロパティ ページ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window))。

ActiveX コントロールの一部として付属するプロパティ シートによって、ActiveX コントロールのプロパティ ページには、さまざまなタブが表示されます。

> [!NOTE]
> 次の手順では、プロパティ ページを使用して ActiveX コントロールを編集するには適用されます。 参照および新しい ActiveX プロパティを編集することができますも**プロパティ**ウィンドウ。

1. 選択、 **ActiveX**コントロール。

1. **ビュー**メニューの **プロパティ ページ**プロパティを表示します。

1. プロパティ ページで、必要に応じて変更を加えます。

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには

ボタン以外のダイアログ ボックス コントロールのメンバー変数を定義するには、次の手順を使用できます。

> [!NOTE]
> このプロセスは、MFC プロジェクト内のダイアログ コントロールにのみ適用されます。 ATL プロジェクトで使用する必要があります、**新しい Windows メッセージおよびイベント ハンドラー**  ダイアログ ボックス。 詳細については、次を参照してください[メッセージの種類は、ユーザー インターフェイス オブジェクトに関連付けられた](../mfc/reference/message-types-associated-with-user-interface-objects.md)、[メッセージ ハンドラーの編集](../mfc/reference/editing-a-message-handler.md)、および[リフレクションメッセージ用のメッセージハンドラーを定義する](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. [ダイアログ エディター](../windows/dialog-editor.md)コントロールを選択します。

1. キーを押しながら、 **Ctrl**キーをダイアログ ボックス コントロールをダブルクリックします。

   [メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)が表示されます。

1. 適切な情報を入力、**メンバー変数の追加**ウィザード。 詳細については、次を参照してください。[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)します。

1. 選択**OK**に戻る、**ダイアログ**エディター。

   > [!TIP]
   > ダイアログ ボックス コントロールから既存のハンドラーにジャンプするには、コントロールをダブルクリックします。

使用することも、**メンバー変数** タブで、 [MFC クラス ウィザード](../mfc/reference/mfc-class-wizard.md)に指定したクラスの新しいメンバー変数を追加し、既に定義されているメンバー変数を表示します。

## <a name="to-delete-a-control"></a>コントロールを削除するには

ダイアログ ボックスで、選択コントロールとキーを押して、**削除**キー。

   \- または -

**編集**メニューの **削除**します。

   > [!TIP]
   > 使用しているときに、**ダイアログ**エディターの多くの場合で、頻繁に使用されるコマンドのショートカット メニューを表示する、マウスの右ボタンをクリックすることができます。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](controls-in-dialog-boxes.md)<br/>
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>

<!-- excluded links
[Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Adding a Class](../ide/adding-a-class-visual-cpp.md)<br/>
[Adding a Member Function](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Overriding a Virtual Function](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler](../mfc/reference/adding-an-mfc-message-handler.md)
[Declaring a Variable Based on Your New Control Class](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
-->
