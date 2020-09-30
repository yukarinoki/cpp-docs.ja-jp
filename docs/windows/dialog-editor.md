---
title: ダイアログエディター (C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
- vc.editors.dialog
helpviewer_keywords:
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
- Dialog Editor [C++], shortcut keys
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
ms.openlocfilehash: 6a83640bd50d4af40be3cdb7a47b29ae5ffb3f09
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504547"
---
# <a name="dialog-editor-c"></a>ダイアログエディター (C++)

**ダイアログエディター**では、ダイアログボックスのリソースを作成または編集できます。

- エディターを開くには、[**リソースビュー** ] ウィンドウでダイアログの .rc ファイルをダブルクリックするか、または [メニューの**表示**] [  >  **その他の Windows**リソースビュー] の順に選択  >  **Resource View**します。

新しいダイアログボックスまたはダイアログボックステンプレートを作成する最初の手順の1つは、コントロールの追加です。 **ダイアログエディター**では、特定のサイズ、形状、または配置に合わせてコントロールを配置したり、ダイアログボックス内で作業するようにコントロールを移動したりすることができます。 また、コントロールは簡単に削除できます。

ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。

**ダイアログエディター**では、1つまたは複数のコントロールのプロパティを編集することもできます。 タブオーダー、つまり **tab** キーが押されたときにコントロールがフォーカスを取得する順序を変更したり、ユーザーがキーボードを使用してコントロールを選択できるアクセスキーまたはキーの組み合わせを定義したりすることができます。

**ダイアログエディター**では、ActiveX コントロールなどのカスタムコントロールを使用することもできます。 [フォームビュー](../mfc/reference/cformview-class.md)、[レコードビュー](../data/record-views-mfc-data-access.md)、または[ダイアログバー](../mfc/dialog-bars.md)を編集することもできます。

Visual Studio 2015 以降では、 **ダイアログエディター** を使用して動的レイアウトを定義できます。動的レイアウトでは、ユーザーがダイアログボックスのサイズを変更したときにコントロールの移動方法とサイズを変更する方法を指定します。 詳細については、「 [Dynamic Layout](../mfc/dynamic-layout.md)」を参照してください。

リソースの詳細については、「 [ダイアログボックス](../windows/creating-a-new-dialog-box.md) および [ダイアログボックスコントロール](../windows/controls-in-dialog-boxes.md)を作成する方法」を参照してください。

> [!TIP]
> **ダイアログエディター**を使用しているときは、多くの場合、マウスの右ボタンをクリックすると、頻繁に使用するコマンドのショートカットメニューを表示できます。

## <a name="dialog-editor-toolbar"></a>ダイアログ エディター ツール バー

**ダイアログエディター**のツールバーには、サイズや配置など、ダイアログボックス上のコントロールのレイアウトを配置するためのボタンが含まれています。 **ダイアログエディター** のツールバーボタンは、[ **書式** ] メニューのコマンドに対応しています。

|アイコン|意味|アイコン|意味|
|----------|-------------|----------|-------------|
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|[ダイアログのテスト]|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|[左右]|
|![左揃えボタン](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|[左揃え]|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|[下へ]|
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|[右揃え]|![幅を揃えるボタン](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|[同じ幅に揃える]|
|![上揃えボタン](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|[上揃え]|![高さを揃えるボタン](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|[同じ高さに揃える]|
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|[下揃え]|![同じサイズに揃えるボタン](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|[同じサイズに揃える]|
|![垂直方向の中央揃えボタン](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Vertical|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|グリッドの切り替え|
|![水平方向の中央揃えボタン](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|水平|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|[ガイドの切り替え]|

- **ダイアログエディター**のツールバーを表示または非表示にするには、メニュー**ビュー**の [  >  **ツールバー**  >  **] ダイアログエディター**にアクセスします。

C++ プロジェクトで **ダイアログエディター** を開くと、ソリューションの最上部に [ **ダイアログエディター** ] ツールバーが自動的に表示されます。ただし、ツールバーを明示的に閉じる場合は、 **ダイアログエディター**を次回開いたときに呼び出す必要があります。 表示を切り替えるには、使用可能なツールバーとウィンドウの一覧から選択します。

## <a name="switch-between-dialog-box-controls-and-code"></a>ダイアログボックスコントロールとコードの切り替え

MFC アプリケーションでは、ダイアログボックスコントロールをダブルクリックすると、そのハンドラーコードにジャンプしたり、スタブハンドラー関数をすばやく作成したりできます。

コントロールを選択した状態で、[プロパティウィンドウ](/visualstudio/ide/reference/properties-window)の [ **ControlEvents** ] ボタンまたは [**メッセージ**] ボタンを選択して、選択した項目で使用可能な Windows メッセージとイベントの完全な一覧を表示します。 ハンドラー関数を作成または編集するには、一覧から選択します。

- **ダイアログエディター**からコードに移動するには、ダイアログボックス内のコントロールをダブルクリックして、最後に実装されたメッセージ処理関数の宣言に移動します。

   ATL ベースのダイアログクラスの場合は、常にコンストラクターの定義に移動します。

- コントロールのイベントを表示するには、コントロールを選択し、[**プロパティ**] ウィンドウの [ **ControlEvents** ] ボタンをクリックします。

   ダイアログボックスに1つのコントロールにフォーカスがある場合は、右クリックして [ **イベントハンドラーの追加**] を選択します。 これにより、ハンドラーを追加するクラスを指定できます。 詳細については、「 [イベントハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)」を参照してください。

   > [!NOTE]
   > ダイアログボックスにフォーカスがあるときに [ **ControlEvents** ] ボタンをクリックすると、ダイアログボックス内のすべてのコントロールの一覧が表示されます。このダイアログボックスを展開して、個々のコントロールのイベントを編集できます。

- ダイアログボックスのメッセージを表示するには、ダイアログボックスをオンにして、[**プロパティ**] ウィンドウの [**メッセージ**] をクリックします。

## <a name="accelerator-keys"></a>アクセラレータ キー

**ダイアログエディター**のコマンドの既定のアクセラレータキーを次に示します。  

|command|[キー]|説明|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl**  + **Shift**  + **下方向キー**|選択したコントロールの下端を最も優先されるコントロールに揃えます。|
|Format.AlignCenters|**Shift**  + **F9**|選択したコントロールの垂直方向の中心を、最も重要なコントロールに揃えます。|
|Format.AlignLefts|**Ctrl**  + **Shift**  + **左方向キー**|選択したコントロールの左端を最も優先されるコントロールに揃えます。|
|Format.AlignMiddles|**F9**|選択したコントロールの水平方向の中心を、最も重要なコントロールに揃えます。|
|Format.AlignRights|**Ctrl**  + **Shift**  + **右方向キー**|選択したコントロールの右端を最も優先されるコントロールに揃えます。|
|Format.AlignTops|**Ctrl**  + **Shift**  + **上矢印**|選択したコントロールの上端を最も優先されるコントロールに揃えます。|
|Format.ButtonBottom|**Ctrl** + **B**|選択したボタンをダイアログボックスの下部中央に配置します。|
|Format.ButtonRight|**Ctrl**  + **R**|選択したボタンをダイアログボックスの右上隅に配置します。|
|Format.CenterHorizontal|**Ctrl**  + **Shift**  + **F9**|コントロールをダイアログボックス内で水平方向に中央揃えにします。|
|Format.CenterVertical|**Ctrl** + **F9**|ダイアログボックス内のコントロールを垂直方向に中央揃えで配置します。|
|Format.CheckMnemonics|**Ctrl**  + **M**|ニーモニックの一意性を確認します。|
|SizeToContent のフォーマット|**Shift**  + **F7**|選択したコントロールのサイズをキャプションテキストに合わせて変更します。|
|Format.SpaceAcross|**Alt**  + **左方向キー**|選択したコントロールを水平方向にスペースで並べます。|
|Format.SpaceDown|**Alt**  + **下方向キー**|選択したコントロールを垂直方向にスペースで並べます。|
|Format.TabOrder|**Ctrl** + **D**|ダイアログ内のコントロールの順序を設定します。|
|Format.TestDialog|**Ctrl** + **T**|ダイアログボックスを実行して、外観と動作をテストします。|
|Format.ToggleGuides|**Ctrl**  + **G**|ダイアログ編集用のグリッドなし、ガイドライン、グリッドの間を切り替えます。|

- ショートカットキーを変更するには、[メニュー**ツール**] [オプション] に移動  >  **Options**し、[**環境**] フォルダーの下の [**キーボード**] を選択します。

   詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。

- 設定を変更するには、[メニュー**ツール**] [  >  **設定のインポートとエクスポート**] に移動します。

   ダイアログボックスで使用できるオプション、および表示されるメニューコマンドの名前と場所は、アクティブな設定またはエディションによっては、 **ヘルプ** で説明されている内容と異なる場合があります。  詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソースエディター](../windows/resource-editors.md)<br/>
[方法: ダイアログボックスを作成する](../windows/creating-a-new-dialog-box.md)<br/>
[ダイアログボックスコントロール](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/adding-a-member-variable-visual-cpp.md#dialog-box-controls-and-variable-types)-->
