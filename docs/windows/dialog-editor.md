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
ms.openlocfilehash: f1544d3a8e14f9373e21b77d888860d24ab1ed6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370286"
---
# <a name="dialog-editor-c"></a>ダイアログ エディター (C++)

**ダイアログ エディター**では、ダイアログ ボックス リソースを作成または編集できます。

- エディタを開くには、ダイアログの .rc ファイルを **[リソース ビュー]** ウィンドウでダブルクリックするか、またはメニューの **[** > **他の Windows** > **リソース ビュー**を表示] に移動します。

新しいダイアログ ボックスまたはダイアログ ボックス テンプレートを作成する最初の手順の 1 つは、コントロールの追加です。 ダイアログ**エディター**では、コントロールを特定のサイズ、形状、または配置に合わせて配置したり、コントロールを移動してダイアログ ボックス内で作業することができます。 また、コントロールは簡単に削除できます。

ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。

**ダイアログ エディター**で、1 つまたは複数のコントロールのプロパティを編集することもできます。 タブオーダー、つまり **、Tab**キーを押したときにコントロールがフォーカスを得る順序を変更したり、キーボードを使用してコントロールを選択できるアクセスキーまたはキーの組み合わせを定義したりできます。

**ダイアログ エディター**では、ActiveX コントロールなどのカスタム コントロールを使用することもできます。 [フォーム ビュー](../mfc/reference/cformview-class.md)、レコード[ビュー](../data/record-views-mfc-data-access.md)、または[ダイアログ バー](../mfc/dialog-bars.md)を編集することもできます。

Visual Studio 2015 以降では、**ダイアログ エディター**を使用して、ユーザーがダイアログのサイズを変更したときにコントロールがどのように移動およびサイズ変更するかを指定する動的レイアウトを定義できます。 詳細については、「 [Dynamic Layout](../mfc/dynamic-layout.md)」を参照してください。

リソースの詳細については、「 ダイアログ ボックス コントロールとダイアログ ボックス[コントロール](../windows/controls-in-dialog-boxes.md)[を作成](../windows/creating-a-new-dialog-box.md)する方法 」を参照してください。

> [!TIP]
> **ダイアログ エディタ**を使用する場合は、多くの場合、マウスの右ボタンを使用して選択すると、頻繁に使用するコマンドのショートカット メニューを表示できます。

## <a name="dialog-editor-toolbar"></a>ダイアログ エディター ツール バー

**ダイアログ エディター**ツールバーには、サイズや配置など、ダイアログ ボックス上のコントロールのレイアウトを配置するためのボタンがあります。 **ダイアログ エディター**のツール バー ボタンは **、[書式]** メニューのコマンドに対応します。

|アイコン|意味|アイコン|意味|
|----------|-------------|----------|-------------|
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "ダイアログ ボックス")|[ダイアログのテスト]|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "アクロス")|[左右]|
|![左揃えボタン](../mfc/media/vcdialogeditoralignlefts.png "左揃え")|[左揃え]|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "をクリックします。")|[下へ]|
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "プロパティを整列します。")|[右揃え]|![幅を揃えるボタン](../mfc/media/vcdialogeditorsamewidth.png "同じ幅")|[同じ幅に揃える]|
|![上揃えボタン](../mfc/media/vcdialogeditoraligntops.png "整列します。")|[上揃え]|![高さを揃えるボタン](../mfc/media/vcdialogeditormakesameheight.png "をクリックします。")|[同じ高さに揃える]|
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "ボトムスを整列させる")|[下揃え]|![同じサイズに揃えるボタン](../mfc/media/vcdialogeditorsamesize.png "同じサイズ")|[同じサイズに揃える]|
|![垂直方向の中央揃えボタン](../mfc/media/vcdialogeditorvertical.png "垂直")|Vertical|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "トグルグリッド")|グリッドの切り替え|
|![水平方向の中央揃えボタン](../mfc/media/vcdialogeditorhorizontal.png "水平なエディター")|水平|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "トグルガイド")|[ガイドの切り替え]|

- **ダイアログ エディター**のツールバーの表示/非表示を切り替えるには、メニューの **[ツールバー** > **の** > 表示 **] ダイアログ エディター**に移動します。

**C++** プロジェクトでダイアログ エディターを開くと、**ダイアログ エディター**のツール バーがソリューションの上部に自動的に表示**されます。** 使用可能なツールバーとウィンドウの一覧から表示を切り替えるには、その表示を切り替えます。

## <a name="switch-between-dialog-box-controls-and-code"></a>ダイアログ ボックス コントロールとコードの切り替え

MFC アプリケーションでは、ダイアログ ボックス コントロールをダブルクリックして、ハンドラ コードにジャンプしたり、スタブ ハンドラ関数をすばやく作成したりできます。

コントロールを選択した状態で **、ControlEvents**ボタンまたは[[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)の **[メッセージ]** ボタンを選択して、選択した項目で使用できる Windows メッセージとイベントの完全な一覧を表示します。 リストから選択して、ハンドラ関数を作成または編集します。

- **ダイアログ エディター**からコードにジャンプするには、ダイアログ ボックス内のコントロールをダブルクリックして、最後に実装されたメッセージ処理関数の宣言にジャンプします。

   ATL ベースのダイアログ クラスの場合は、常にコンストラクター定義にジャンプします。

- コントロールのイベントを表示するには、コントロールを選択し、[**プロパティ]** ウィンドウの **[ControlEvents]** ボタンをクリックします。

   ダイアログ ボックスで 1 つのコントロールにフォーカスがある場合は、右クリックして [**イベント ハンドラの追加**] を選択します。 これにより、ハンドラーを追加するクラスを指定できます。 詳細については、「[イベント ハンドラの追加](../ide/adding-an-event-handler-visual-cpp.md)」を参照してください。

   > [!NOTE]
   > ダイアログ ボックスにフォーカスがあるときに**ControlEvents**ボタンを選択すると、ダイアログ ボックス内のすべてのコントロールの一覧が表示され、展開して個々のコントロールのイベントを編集できます。

- ダイアログ ボックスのメッセージを表示するには、ダイアログ ボックスを選択し、[**プロパティ]** ウィンドウの [**メッセージ**] ボタンをクリックします。

## <a name="accelerator-keys"></a>アクセラレータ キー

**ダイアログ エディター**コマンドの既定のアクセラレータ キーを次に示します。  

|command|[キー]|説明|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl** + **シフト** + **下矢印**|選択したコントロールの下端を、最も優先度の高いコントロールに揃えます。|
|Format.AlignCenters|**シフト** + **F9**|選択したコントロールの垂直方向の中央を、最も優先度の高いコントロールに揃えます。|
|Format.AlignLefts|**Ctrl Shift** + **左** + **矢印**|選択したコントロールの左端を、最も優先度の高いコントロールに揃えます。|
|Format.AlignMiddles|**F9**|選択したコントロールの水平方向の中央を、最も優先度の高いコントロールに揃えます。|
|Format.AlignRights|**Ctrl** + **シフト** + **右矢印**|選択したコントロールの右端を、最も優先度の高いコントロールに揃えます。|
|Format.AlignTops|**Ctrl** + **シフト** + **上矢印**|選択したコントロールの上端を、最も優先度の高いコントロールに揃えます。|
|Format.ButtonBottom|**Ctrl** + **B**|選択したボタンをダイアログ ボックスの下部中央に配置します。|
|Format.ButtonRight|**Ctrl** + **R**|選択したボタンをダイアログ ボックスの右上隅に配置します。|
|Format.CenterHorizontal|**Ctrl** + **シフト** + **F9**|ダイアログ ボックス内でコントロールを水平方向に中央揃えします。|
|Format.CenterVertical|**Ctrl** + **F9**|ダイアログ ボックス内のコントロールを垂直方向に中央揃えします。|
|Format.CheckMnemonics|**Ctrl** + **M**|ニーモニックの一意性をチェックします。|
|サイズコンテンツの書式設定|**シフト** + **F7**|選択したコントロールのサイズをキャプション テキストに合わせて変更します。|
|Format.SpaceAcross|**Alt** + **左矢印**|選択したコントロールを水平方向に等間隔で配置します。|
|Format.SpaceDown|**Alt** + **下向き矢印**|選択したコントロールを縦方向に均等に配置します。|
|Format.TabOrder|**Ctrl** + **D**|ダイアログ内のコントロールの順序を設定します。|
|Format.TestDialog|**Ctrl** + **T**|ダイアログ ボックスを実行して、外観と動作をテストします。|
|Format.ToggleGuides|**Ctrl** + **G**|ダイアログ編集のためのグリッド、ガイドライン、グリッドを循環します。|

- ショートカット キーを変更するには、メニュー**の [ツール** > **オプション]** に移動し、[**環境**] フォルダの下の **[キーボード**] を選択します。

   詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。

- 設定を変更するには、メニューの **[ツール** > **のインポートとエクスポートの設定]** に移動します。

   ダイアログ ボックスで使用できるオプション、および表示されるメニュー コマンドの名前と場所は、アクティブな設定やエディションによって**ヘルプ**で説明されている内容と異なる場合があります。  詳細については、「 [IDE の個人用設定](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[[方法] ダイアログ ボックスを作成する](../windows/creating-a-new-dialog-box.md)<br/>
[ダイアログ ボックス コントロール](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->
