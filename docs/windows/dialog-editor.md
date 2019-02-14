---
title: ダイアログ エディター (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 827a7610aa919d5349313346ac0bfa80bd0647b0
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264895"
---
# <a name="dialog-editor-c"></a>ダイアログ エディター (C++)

**ダイアログ**エディターでは、作成またはダイアログ ボックスのリソースを編集することができます。 ダイアログ エディターでダイアログの .rc ファイルをダブルクリックして開く、**リソース ビュー**ウィンドウ (**ビュー** > **リソース ビュー**)。 なお**リソース ビュー** Express エディションでは使用できません。

ダイアログ ボックスまたはダイアログ ボックス テンプレートを新規作成する場合の最初のステップの 1 つは、ダイアログ ボックスにコントロールを追加することです。 **ダイアログ** ダイアログ ボックス内で作業するには、約に移動するか、エディター、特定のサイズ、形状、または配置に合わせてコントロールを配置することができます。 また、コントロールは簡単に削除できます。

ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。

さらに、ダイアログ エディターでは、単一または複数のコントロールのプロパティを編集できます。 タブ オーダーを変更することができます、つまり、フォーカス コントロールを取得する順序、**タブ**キーが押された、またはユーザーがキーボードを使用してコントロールを選択できるアクセス キー (キーの組み合わせ) を定義することができます。 事前に設定されているアクセス キーの一覧については、「 [ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)」を参照してください。

**ダイアログ**エディターでは ActiveX コントロールなどのカスタム コントロールを使用することもできます。 さらに、 [フォーム ビュー](../mfc/reference/cformview-class.md)、 [レコード ビュー](../data/record-views-mfc-data-access.md)、または [ダイアログ バー](../mfc/dialog-bars.md)も編集できます。

Visual Studio 2015 以降では、ダイアログ エディターを使用して、コントロールの移動方法と、ユーザーがダイアログをサイズ変更時にサイズを変更する方法を指定する、動的なレイアウトを定義します。 詳細については、「 [Dynamic Layout](../mfc/dynamic-layout.md)」を参照してください。

- [ダイアログ ボックスの新規作成](../windows/creating-a-new-dialog-box.md)

- [ユーザーが実行時に終了できないダイアログ ボックスの作成](../windows/creating-a-dialog-box-that-users-cannot-exit.md)

- [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)

- [ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)

- [ダイアログ ボックスのテスト](../windows/testing-a-dialog-box.md)

- [ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)

   > [!TIP]
   > 使用しているときに、**ダイアログ**エディターの多くの場合で、頻繁に使用されるコマンドのショートカット メニューを表示する、マウスの右ボタンをクリックすることができます。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="dialog-editor-toolbar"></a>ダイアログ エディター ツール バー

開くと、**ダイアログ**C プロジェクト、エディター、**ダイアログ エディター**ソリューションの上部にあるツールバーが自動的に表示されます。

|アイコン|説明|アイコン|説明|
|----------|-------------|----------|-------------|
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|[ダイアログのテスト]|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|[左右]|
|![左揃えボタン](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|[左揃え]|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|[下へ移動]|
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|[右揃え]|![Make 同じ幅ボタン](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|[同じ幅に揃える]|
|![上揃えボタン](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|[上揃え]|![Make 同じ高さボタン](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|[同じ高さに揃える]|
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|[下揃え]|![同じサイズのボタン](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|[同じサイズに揃える]|
|![垂直方向の中心のボタン](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Vertical|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|グリッドの切り替え|
|![水平方向の中央ボタン](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|[水平方向]|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|[ガイドの切り替え]|

**ダイアログ エディター**ツールバーには、ダイアログ ボックスで、たとえばサイズと配置上のコントロールのレイアウトを変更するためのボタンが含まれています。 **ダイアログ エディター**ツール バー ボタンにコマンドに対応しており、**形式**メニュー。

は、**ダイアログ**エディターの表示を切り替えることができます、**ダイアログ エディター**ツールバーを使用できるツールバーおよびウィンドウの一覧から選択します。

- ダイアログ エディターのツールバーを非表示、**ビュー**メニューの **ツールバー**を選択し、**ダイアログ エディター**サブメニューから。

   > [!NOTE]
   > **ダイアログ エディター**ダイアログ エディターのダイアログ ボックスのリソースを開くと、既定でツールバーが表示されます。 ただし、場合は、ツールバーを明示的に閉じる必要があります ダイアログ ボックスのリソースでは、次に開いた際に、を起動します。

## <a name="switch-between-dialog-box-controls-and-code"></a>ダイアログ ボックスのコントロールとコードの切り替え

MFC アプリケーションで、ハンドラーのコードに移動する、またはハンドラー関数スタブをすばやく作成するためのダイアログ ボックス コントロールをダブルクリックできます。

コントロールを選択すると、をクリックして、**イベント コントロール**ボタンまたは**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)Windows メッセージおよびイベントの完全な一覧を表示するには選択した項目に使用できます。 作成または編集ハンドラー関数の一覧から選択します。

- ダイアログ エディターからコードにジャンプするには、その最後に実装されたメッセージの処理関数の宣言にジャンプ ダイアログ ボックス内のコントロールをダブルクリックします。 (ATL ベースのダイアログ クラスでは、常にジャンプするコンス トラクターの定義。)

- 選択すると、コントロールでのコントロールのイベントを表示するには、選択、**イベント コントロール**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

   > [!NOTE]
   > 選択、**イベント コントロール**ボタン、 * ダイアログ ボックス*し展開すると、個々 のコントロールのイベントの編集 ダイアログ ボックスにフォーカスが公開のすべてのコントロールの一覧があります。

   右クリックして選択できます ダイアログ ボックスの 1 つのコントロールにフォーカスした場合、**イベント ハンドラーの追加**ショートカット メニューから。 これにより、ハンドラーを追加するクラスを指定することができます。 詳細については、次を参照してください。[イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)します。

- メッセージ、ダイアログ ボックスをオンにすると、ダイアログ ボックスを表示するには、選択、**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

## <a name="accelerator-keys"></a>アクセラレータ キー

以下には、アクセラレータ キー ダイアログ エディター コマンドの既定値を示します。 ショートカット キーを変更するには、次のように選択します。**オプション**上、**ツール**] メニューの [選択**キーボード**下、**環境**フォルダー。 詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。

> [!NOTE]
> 使用している設定またはエディションによっては、ダイアログ ボックスで使用可能なオプションや、メニュー コマンドの名前や位置がヘルプに記載されている内容と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

|コマンド|キー|説明|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl キーを押し** + **Shift** + **下矢印をクリック**|主要なコントロールで選択したコントロールの下端に揃えます|
|Format.AlignCenters|**Shift キーを押し** + **F9**|主要なコントロールで選択したコントロールの垂直方向の中央に配置します|
|Format.AlignLefts|**Ctrl キーを押し** + **Shift** + **左向き矢印**|主要なコントロールで選択したコントロールの左揃え|
|Format.AlignMiddles|**F9**|主要なコントロールで選択したコントロールの水平方向の中央に配置します|
|Format.AlignRights|**Ctrl キーを押し** + **Shift** + **右向き矢印**|主要なコントロールで選択したコントロールの右揃え|
|Format.AlignTops|**Ctrl キーを押し** + **Shift** + **上向きの矢印**|主要なコントロールで選択したコントロールの上端を揃えて配置します。|
|Format.ButtonBottom|**Ctrl キーを押し** + **B**|選択したボタンをダイアログ ボックスの下部中央に配置します。|
|Format.ButtonRight|**Ctrl キーを押し** + **R**|選択したボタンをダイアログ ボックスの右上隅に配置します。|
|Format.CenterHorizontal|**Ctrl キーを押し** + **Shift** + **F9**|コントロールをダイアログ ボックス内で水平方向に中央揃え|
|Format.CenterVertical|**Ctrl**  +  **F9**|コントロールをダイアログ ボックス内で垂直方向に中央揃え|
|Format.CheckMnemonics|**Ctrl キーを押し** + **M**|ニーモニックの一意性をチェックします|
|Format.SizeToContent|**Shift キーを押し** + **F7**|選択されたキャプションのテキストに合わせてコントロールのサイズを変更します。|
|Format.SpaceAcross|**Alt**  +  **← キー**|選択したコントロールを水平方向に均等します。|
|Format.SpaceDown|**Alt** + **下矢印をクリック**|選択したコントロールを垂直方向に均等します。|
|Format.TabOrder|**Ctrl**  +  **D**|ダイアログ ボックス内のコントロールの順序を設定します。|
|Format.TestDialog|**Ctrl**  +  **T**|ダイアログ ボックスの外観と動作をテストの実行します。|
|Format.ToggleGuides|**Ctrl**  +  **G**|ダイアログを編集するためのないグリッド、ガイドライン、およびグリッド間サイクル|

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソースを作成する](../windows/how-to-create-a-resource.md)<br/>
[コントロール](../mfc/controls-mfc.md)<br/>
[コントロール クラス](../mfc/control-classes.md)<br/>
[ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)<br/>
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)