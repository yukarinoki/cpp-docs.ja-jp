---
title: ダイアログ エディター (C++)
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
ms.openlocfilehash: dc5a823951e07af96efceec52d2aa23552c2d002
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414323"
---
# <a name="dialog-editor-c"></a>ダイアログ エディター (C++)

**ダイアログ エディター**  ダイアログ ボックスのリソースを作成または更新することができます。

- ダイアログの .rc ファイルをダブルクリックしてエディターを開くには、**リソース ビュー**ウィンドウ、またはメニューに移動して**ビュー** > **リソース ビュー**します。

コントロールを追加する新しい ダイアログ ボックスまたはダイアログ ボックス テンプレートを作成する最初の手順の 1 つです。 **ダイアログ エディター**を移動して、ダイアログ ボックス内で作業するには、約や特定のサイズ、形状、または配置に合わせてコントロールを配置することができます。 また、コントロールは簡単に削除できます。

ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。

1 つのプロパティを編集することも、または複数のコントロールで、**ダイアログ エディター**します。 タブ オーダーを変更することができます、つまり、フォーカス コントロールを取得する順序、**タブ**キーを押すか、アクセス キーまたはキーボードを使用してコントロールを選択できるキーの組み合わせを定義することができます。

**ダイアログ エディター** ActiveX コントロールなどのカスタム コントロールを使用することもできます。 編集することも、[フォーム ビュー](../mfc/reference/cformview-class.md)、[ビューを記録](../data/record-views-mfc-data-access.md)、または[ダイアログ バー](../mfc/dialog-bars.md)します。

Visual Studio 2015 以降を使えば、**ダイアログ エディター**ユーザーがダイアログをサイズ変更時に動的なレイアウトは、コントロールの移動を指定し、サイズ変更を定義します。 詳細については、「 [Dynamic Layout](../mfc/dynamic-layout.md)」を参照してください。

リソースの詳細については、次を参照してください。 方法[作成 ダイアログ ボックス](../windows/creating-a-new-dialog-box.md)と[ダイアログ ボックス コントロール](../windows/controls-in-dialog-boxes.md)します。

> [!TIP]
> 使用しているときに、**ダイアログ エディター**、頻繁に使用されるコマンドのショートカット メニューを表示する多くの場合、マウスの右ボタンで選択できます。

## <a name="dialog-editor-toolbar"></a>ダイアログ エディター ツール バー

**ダイアログ エディター**ツールバーには、ダイアログ ボックスで、たとえばサイズと配置上のコントロールのレイアウトを変更するためのボタンが含まれています。 **ダイアログ エディター**ツール バー ボタンにコマンドに対応しており、**形式**メニュー。

|アイコン|説明|アイコン|説明|
|----------|-------------|----------|-------------|
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|[ダイアログのテスト]|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|[左右]|
|![左揃えボタン](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|[左揃え]|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|[下へ移動]|
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|[右揃え]|![Make 同じ幅ボタン](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|[同じ幅に揃える]|
|![上揃えボタン](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|[上揃え]|![Make 同じ高さボタン](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|[同じ高さに揃える]|
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|[下揃え]|![同じサイズのボタン](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|[同じサイズに揃える]|
|![垂直方向の中心のボタン](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Vertical|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|グリッドの切り替え|
|![水平方向の中央ボタン](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|[水平方向]|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|[ガイドの切り替え]|

- 非表示、**ダイアログ エディター**ツールバー、メニューに移動して**ビュー** > **ツールバー** > **ダイアログ エディター**。

開くと、**ダイアログ エディター** C++ プロジェクトで、**ダイアログ エディター**ソリューションの上部にあるツールバーが自動的に表示されます、ただし場合は、ツールバーを明示的に閉じると、する必要がありますを呼び出すこと、次に開いたとき、**ダイアログ エディター**します。 使用可能なツールバーと windows の一覧から選択して、その表示を切り替えることができます。

## <a name="switch-between-dialog-box-controls-and-code"></a>ダイアログ ボックスのコントロールとコードの切り替え

MFC アプリケーションで、ハンドラーのコードに移動する、またはハンドラー関数スタブをすばやく作成するためのダイアログ ボックス コントロールをダブルクリックできます。

コントロールを選択すると、選択、**イベント コントロール**ボタンまたは**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)Windows メッセージおよびイベントの完全な一覧を表示するには選択した項目に使用できます。 作成または編集ハンドラー関数の一覧から選択します。

- コードに移動する、**ダイアログ エディター**、その最後に実装されたメッセージの処理関数の宣言にジャンプ ダイアログ ボックス内のコントロールをダブルクリックします。

   ATL ベースのダイアログ クラスでは、常に、コンス トラクターの定義にジャンプします。

- 選択すると、コントロールでのコントロールのイベントを表示するのには、選択、**イベント コントロール**ボタン、**プロパティ**ウィンドウ。

   右クリックして選択できます ダイアログ ボックスの 1 つのコントロールにフォーカスした場合、**イベント ハンドラーの追加**します。 これにより、ハンドラーを追加するクラスを指定することができます。 詳細については、次を参照してください。[イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)します。

   > [!NOTE]
   > 選択、**イベント** ダイアログ ボックスにフォーカスがあるときにボタンがダイアログ ボックスで、展開すると、個々 のコントロールのイベントを編集し、すべてのコントロールの一覧を公開します。

- メッセージ、ダイアログ ボックスをオンにすると、ダイアログ ボックスを表示するには、選択、**メッセージ**ボタン、**プロパティ**ウィンドウ。

## <a name="accelerator-keys"></a>アクセラレータ キー

次のとおり、既定のアクセラレータ キー、**ダイアログ エディター**コマンド。  

|コマンド|キー|説明|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl キーを押し** + **Shift** + **下矢印をクリック**|主要なコントロールで選択したコントロールの下端に揃えて配置します。|
|Format.AlignCenters|**Shift キーを押し** + **F9**|主要なコントロールで選択したコントロールの垂直方向の中央に揃えます。|
|Format.AlignLefts|**Ctrl キーを押し** + **Shift** + **左向き矢印**|主要なコントロールで選択したコントロールの左揃えにします。|
|Format.AlignMiddles|**F9**|主要なコントロールで選択したコントロールの水平方向の中央に配置します。|
|Format.AlignRights|**Ctrl キーを押し** + **Shift** + **右向き矢印**|主要なコントロールで選択したコントロールの右揃えにします。|
|Format.AlignTops|**Ctrl キーを押し** + **Shift** + **上向きの矢印**|主要なコントロールで選択したコントロールの上端を揃えて配置します。|
|Format.ButtonBottom|**Ctrl キーを押し** + **B**|選択したボタンを ダイアログ ボックスの下部中央に配置します。|
|Format.ButtonRight|**Ctrl キーを押し** + **R**|ダイアログ ボックスの右上隅にある、選択したボタンを配置します。|
|Format.CenterHorizontal|**Ctrl キーを押し** + **Shift** + **F9**|コントロールをダイアログ ボックス内で水平方向に中央揃え。|
|Format.CenterVertical|**Ctrl**  +  **F9**|コントロールをダイアログ ボックスの垂直方向に中央揃えにします。|
|Format.CheckMnemonics|**Ctrl キーを押し** + **M**|ニーモニックの一意性を確認します。|
|Format.SizeToContent|**Shift キーを押し** + **F7**|選択されたキャプションのテキストに合わせてコントロールのサイズを変更します。|
|Format.SpaceAcross|**Alt**  +  **← キー**|選択したコントロールを水平方向に等間隔します。|
|Format.SpaceDown|**Alt** + **下矢印をクリック**|選択したコントロールを垂直方向に等間隔します。|
|Format.TabOrder|**Ctrl**  +  **D**|ダイアログ ボックス内のコントロールの順序を設定します。|
|Format.TestDialog|**Ctrl**  +  **T**|ダイアログ ボックスの外観と動作をテストを実行します。|
|Format.ToggleGuides|**Ctrl**  +  **G**|ダイアログを編集するためありませんグリッド、ガイドライン、およびグリッド間で切り替えます。|

- ショートカット キーを変更するには、メニューに移動**ツール** > **オプション**、選択**キーボード**下、**環境**フォルダー。

   詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。

- 設定を変更するには、メニューに移動**ツール** > **インポートおよびエクスポート設定**します。

   記載されているどのようなダイアログ ボックスで、名前、およびメニュー コマンドの場所で使用可能なオプションが異なる場合があります**ヘルプ**アクティブな設定またはエディションによって異なります。  詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[方法: ダイアログ ボックスを作成する](../windows/creating-a-new-dialog-box.md)<br/>
[ダイアログ ボックス コントロール](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->