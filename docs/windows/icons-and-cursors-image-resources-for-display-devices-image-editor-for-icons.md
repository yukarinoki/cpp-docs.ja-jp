---
title: アイコンとカーソル:ディスプレイ デバイス (C++ アイコン用イメージ エディター) のイメージ リソース
ms.date: 11/04/2016
f1_keywords:
- vc.editors.icon
- vc.editors.newimagetype
- vc.editors.customimage
- vc.editors.opendeviceimage
- vc.editors.image.editing
helpviewer_keywords:
- cursors [C++], creating
- image resources [C++], display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices [C++], creating icons for
- cursors [C++], hot spots
- icons [C++], types
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
- New <Device> Image Type dialog box [C++]
- Custom Image dialog box [C++]
- Open <Device> Image dialog box [C++]
- New Device Image command
- display devices [C++], adding images
- cursors [C++], adding
- icons, adding
- display devices [C++], copying images
- cursors [C++], copying
- icons, copying
- cursors [C++], deleting
- display devices [C++], deleting device image
- icons, erasing
- icons, deleting
- cursors [C++], undoing changes
- icons, undoing changes
- cursors [C++], screen regions
- inverse colors [C++], device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices [C++], transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects [C++], transparent images
- icons [C++], screen regions
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
- colors [C++], icons and cursors
- color palettes, 256-color
- palettes, 256-color
- cursors [C++], hot spots
- hot spots
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
ms.openlocfilehash: 027c3c0380a73c624432bbe45758b3296732949a
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849946"
---
# <a name="icons-and-cursors-image-resources-for-display-devices-c-image-editor-for-icons"></a>アイコンとカーソル:ディスプレイ デバイス (C++ アイコン用イメージ エディター) のイメージ リソース

アイコンとカーソルは、グラフィカルなリソースで、表示デバイスの種類ごとに異なるサイズや色スキームの複数のイメージを含めることができます。 カーソルの位置を追跡するために Windows を使用して場所する「ホット スポット」があります。 アイコンとカーソルの両方が作成され、編集を使用して、**イメージ**エディターで、ビットマップ、およびその他のイメージ。

新しいアイコンまたはカーソルを作成するときに、**イメージ**エディターが最初に、標準タイプのイメージを作成します。 イメージは最初、画面の色 (透明) で塗られます。 イメージがカーソルの場合、ホット スポットは最初、左上隅 (座標 0,0) に置かれます。

既定で、**イメージ**エディターは、次の表に示すようにデバイスの追加イメージの作成をサポートしています。 幅、高さ、色の数のパラメーターを [[カスタム イメージの種類]](custom-image-dialog-box-image-editor-for-icons.md)ダイアログ ボックスに入力することにより、その他のデバイス用のイメージを作成することができます。

> [!NOTE]
> 使用して、**イメージ エディター**、32 ビットのイメージを表示することができますが、編集することはできません。

|色|幅 (ピクセル単位)|高さ (ピクセル単位)|
|-----------|----------------------|-----------------------|
|白黒|16|16|
|白黒|32|32|
|白黒|48|48|
|白黒|64|64|
|白黒|96|96|
|16|16|16|
|16|32|32|
|16|64|64|
|16|48|48|
|16|96|96|
|256|16|16|
|256|32|32|
|256|48|48|
|256|64|64|
|256|96|96|

## <a name="create-a-device-image-icon-or-cursor"></a>デバイスのイメージ (アイコンやカーソル) の作成します。

新しいアイコンやカーソルのリソースを作成するときに、**イメージ**エディターが特定のスタイル (32 × 32 の 16 色のアイコンと 32 × 32、カーソルのモノクロ) で最初にイメージを作成します。 初期のアイコンやカーソルをさまざまなサイズとスタイルのイメージを追加し、必要に応じて、別のディスプレイ デバイスの各追加のイメージを編集できます。 既存のイメージの種類やグラフィックス プログラムで作成したビットマップからカット アンド ペースト操作を使用してイメージを編集することもできます。

アイコンまたはカーソルのリソースを開くと、[イメージ エディター](../windows/image-editor-for-icons.md)、密接に現在のディスプレイ デバイスを照合ほとんどが既定で表示するイメージ。

### <a name="new-ltdevicegt-image-type-dialog-box"></a>新しい&lt;デバイス&gt;イメージの種類 ダイアログ ボックス

**新規&lt;デバイス&gt;イメージの種類** ダイアログ ボックスでは、指定した型の新しいデバイス イメージを作成することができます。 開くには、**新規\<デバイス > イメージ**ダイアログ ボックスで、**イメージ タイプの新規**上、**イメージ**メニュー。 次のプロパティが含まれている**ターゲット イメージ タイプ**と**カスタム**します。

#### <a name="target-image-type"></a>ターゲット イメージ タイプ

使用可能なイメージの種類を一覧表示します。 開きたい画像の種類を選択します。

||||
|-|-|-|
|の 16 x 16 16 色|-48 48 x 16 色|-96 x 96 16 色|
|-16 x 16、256 色|-48 x 48 256 色|-96 x 96 256 色|
|-16 x 16、モノクロ|-48、モノクロ x 48|-96、モノクロ x 96|
|-32 x 32 の 16 色|x64 では、64 16 色||
|-32 x 32、256 色|x64 では、64 256 色||
|-32 x 32、モノクロ|x 64、モノクロ 64||

> [!NOTE]
> 既存のイメージは、この一覧に表示されません。

#### <a name="custom"></a>カスタム

開く、**カスタム イメージ**ダイアログ ボックスでカスタムのサイズと色の数を新しいイメージを作成できます。

**カスタム イメージ** ダイアログ ボックスでは、カスタムのサイズと色の数で新しいイメージを作成することができます。 次のプロパティは次のとおりです。

|プロパティ|説明|
|---|---|
|**Width**|カスタム イメージの幅をピクセル (1 ~ 512 の制限を 2048) で入力する場所を提供します。|
|**Height**|ピクセル (1 ~ 512 の制限を 2048) でカスタム イメージの高さを入力する場所を提供します。|
|**色**|カスタム イメージの色の数を選択する場所を提供します。2、16、または 256 です。|

### <a name="open-ltdevicegt-image-dialog-box"></a>開いている&lt;デバイス&gt;イメージ ダイアログ ボックス

使用して、**開く&lt;デバイス&gt;イメージ**を C++ プロジェクトでデバイスのイメージを開く ダイアログ ボックス。 現在のリソース (現在のリソースの一部であるイメージ) の既存のデバイスのイメージが一覧表示します。 次のプロパティは次のとおりです。

|プロパティ|説明|
|---|---|
|**現在のイメージ**|リソースに含まれるイメージを一覧表示します。 開きたい画像の種類を選択します。|

### <a name="to-create-a-new-icon-or-cursor"></a>新しいアイコンやカーソルを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし**リソースの挿入**ショートカット メニューからです。 (を右クリックしてなど、カーソル、.rc ファイルに既存のイメージ リソースが既にある場合、**カーソル**フォルダーと選択**挿入カーソル**ショートカット メニューから)。

   > [!NOTE]
   > 場合は、プロジェクトに .rc ファイル含まれていないを参照してください。[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)です。

1. [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)を選択します**アイコン**または**カーソル**選択**新規**します。 アイコンには、この操作は、32 × 32、16 色のアイコンのアイコン リソースを作成します。 カーソルの場合は 32 × 32、モノクロの (2 色) イメージが作成されます。

   プラス記号の場合 (**+**) でイメージ リソースの種類の横に表示、**リソースの挿入**ダイアログ ボックスで、ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択して、選択、プラス記号を選択します。**新規**します。

## <a name="add-an-image-for-a-different-display-device"></a>別のディスプレイ デバイスのイメージを追加します。

1. **イメージ**メニューの **新しいデバイス イメージ**(内を右クリックし、または、**イメージ エディター**ウィンドウ選択**新しいデバイス イメージ**から、ショートカット メニューの場合)。

1. 追加するイメージの種類を選択します。 選択することも**カスタム**サイズが既定の一覧では使用できません。 アイコンを作成します。

## <a name="copy-a-device-image"></a>デバイス イメージをコピーします。

1. **イメージ**メニューの **デバイス イメージを開いて**と現在のイメージ リストからイメージを選択します。 たとえば、32 × 32 の 16 色のバージョンのアイコンを選択します。

1. 現在表示されているアイコンのイメージのコピー (**Ctrl**+**C**)。

1. 別のアイコンの別のイメージを開く**イメージ エディター**ウィンドウ。 たとえば、16 × 16 の 16 色のバージョンのアイコンを開きます。

1. アイコン イメージを貼り付けます (**Ctrl**+**V**) から 1 つ**イメージ エディター**他のウィンドウ。 小さいサイズに大きなサイズのデータを貼り付ける場合は、イメージのサイズを変更するアイコンのハンドルを使用できます。

## <a name="delete-a-device-image"></a>デバイス イメージを削除します。

アイコン イメージが表示されますが、**イメージ**エディターで、**デバイス イメージの削除**から、**イメージ**メニュー。 リソースの最後のアイコン イメージを削除すると、リソースも削除されます。

   > [!NOTE]
   > 押したときに、 **Del**キー、イメージとアイコンを描画する色は削除されますが、アイコンは今すぐ再設計できることです。 キーを押す場合**Del**押すと、誤って**Ctrl**+**Z**アクションを元に戻す。

## <a name="create-transparent-or-inverse-regions-in-device-images"></a>デバイス イメージの透明または反転領域を作成します。

[イメージ エディター](../windows/image-editor-for-icons.md)、初期のアイコンまたはカーソルのイメージが透明な属性。 アイコンとカーソルのイメージは四角形が、多くはありませんで表示イメージの部分は透過的です。アイコンまたはカーソルを画面上の基になるイメージを示しています。 アイコンをドラッグするときに、反転色でイメージの部分を引き起こすことがあります。 画面の色との逆の色を設定してこの効果を作成する、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。

画面と反転色のアイコンに適用して、カーソルか図形し色の派生イメージまたは反転領域の割り当ています。 色は、これらの属性を持つイメージの部分を表します。 編集画面の色と反転色の属性を表す色を変更することができます。 これらの変更は、アイコンやカーソルをアプリケーションの外観に影響はありません。

> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、**ヘルプ**の説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

### <a name="to-create-transparent-or-inverse-regions"></a>透明または反転領域を作成するには

1. **色**ウィンドウで、**画面の色**セレクターまたは**反転色**セレクター。

1. 画面描画ツールを使用して、イメージに逆の色を適用します。 描画ツールの詳細については、次を参照してください。[描画ツールを使用して](using-a-drawing-tool-image-editor-for-icons.md)します。

### <a name="to-change-the-screen-or-inverse-color"></a>画面または反転色を変更するには

1. いずれかを選択、**画面の色**セレクターまたは**反転色**セレクター。

1. 色を選択、**色**パレットで、**色**ウィンドウ。

   補色は他のセレクターを自動的に割り当てられます。

   > [!TIP]
   > ダブルクリックする場合、**画面の色**または**反転色**セレクター、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)が表示されます。

## <a name="use-the-256-color-palette"></a>256 色カラー パレットを使用します。

使用して、**イメージ**エディター、アイコンとカーソルは、サイズが設定された大きな (64 × 64) 256 色カラー パレットから選択するとします。 リソースを作成すると、デバイスのイメージのスタイルが選択されます。

### <a name="to-create-a-256-color-icon-or-cursor"></a>256 色のアイコンまたはカーソルを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし**リソースの挿入**ショートカット メニューからです。 (を右クリックしてなど、カーソル、.rc ファイルに既存のイメージ リソースが既にある場合、**カーソル**フォルダーと選択**挿入カーソル**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)を選択します**アイコン**または**カーソル**選択**新規**します。

1. **イメージ**メニューの **新しいデバイス イメージ**します。

1. 256 色の画像のスタイルを選択します。

### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>大きいアイコンの 256 色カラー パレットから色を選択するには

256 色カラー パレットから選択した場合、描画するから色を選択する必要があります、**色**パレットで、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。

1. 大きいアイコンまたはカーソルを選択するか、新しいの大きいアイコンまたはカーソルを作成します。

1. 色で表示される 256 色から選択、**色**パレットで、**色**ウィンドウ。

   選択した色に現在の色になります、**色**パレットで、**色**ウィンドウ。

   > [!NOTE]
   > 256 色の画像に使用する初期のパレットがによって返されるパレットと一致する、 `CreateHalftonePalette` Windows API。 Windows シェルは、すべてのアイコンは、パレットの実現化中のちらつきを防ぐためにこのパレットを使用する必要があります。

## <a name="set-a-cursor39s-hot-spot"></a>カーソルを設定&#39;s ホット スポット

カーソルのホット スポットとは、ポイントにカーソルの位置を追跡することで Windows を参照します。 既定では、ホット スポットがカーソル (座標 0, 0) の左上隅に設定されます。 **ホット スポット**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)ホット スポットの座標を示します。

### <a name="to-set-a-cursors-hot-spot"></a>カーソルのホット スポットを設定するには

1. [イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)、選択、**ホット スポットの設定**ツール。

1. カーソルのホット スポットとして指定するピクセルを選択します。

   **ホット スポット**プロパティ、**プロパティ**ウィンドウには、新しい座標が表示されます。

   > [!TIP]
   > ツール バー ボタンの上にカーソルを置くとツール ヒントが表示されます。 これらのヒントは、各ボタンの機能を識別するのに役立ちます。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[[イメージ] メニュー](../windows/image-menu-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)<br/>
[アイコン](/windows/desktop/menurc/icons)<br/>
[カーソル](/windows/desktop/menurc/cursors)<br/>
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
