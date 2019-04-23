---
title: '方法: アイコンまたはその他のイメージを作成します。'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.newimagetype
- vc.editors.customimage
- vc.editors.opendeviceimage
- vc.editors.image.editing
- vc.editors.image.editing
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resources [C++], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
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
- .gif files [C++], saving bitmaps as
- jpg files [C++], saving bitmaps as
- jpeg files [C++], saving bitmaps as
- .jpg files [C++], saving bitmaps as
- Image editor [C++], converting image formats
- gif files [C++], saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files [C++], saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
- images [C++], stand-alone editing
- Image editor [C++], converting image formats
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
ms.openlocfilehash: d10593ffbae7aef55adc3334057402b6952d8ba7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027598"
---
# <a name="how-to-create-an-icon-or-other-image"></a>方法: アイコンまたはその他のイメージを作成します。

新しいイメージ、ビットマップ、アイコン、カーソル、またはツールバーを作成し、使用することができます、**イメージ エディター**その外観をカスタマイズします。 後でパターン化、新しいビットマップを作成することも、[リソース テンプレート](../windows/how-to-use-resource-templates.md)します。

## <a name="icons-and-cursors-image-resources-for-display-devices"></a>アイコンとカーソル:ディスプレイ デバイスのイメージ リソース

アイコンとカーソルは、グラフィカルなリソースで、表示デバイスの種類ごとに異なるサイズや色スキームの複数のイメージを含めることができます。 カーソルはホット スポットもあります、場所の Windows を使用して、位置を追跡します。 アイコンとカーソルの両方が作成され、編集を使用して、**イメージ エディター**ビットマップやその他のイメージと同様、します。

新しいアイコンまたはカーソルを作成するときに、**イメージ エディター**最初に、標準タイプのイメージを作成します。 イメージは最初、画面の色 (透明) で塗られます。 ホット スポットは、最初の座標で左上隅にあるイメージがカーソルの場合は、`0,0`します。

既定で、**イメージ エディター**次の表に示すようにデバイスの他のイメージの作成をサポートします。 その他のデバイス用のイメージを作成するには幅、高さ、および色の数のパラメーターを入力して、**カスタム イメージ** ダイアログ ボックス。

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

### <a name="create-a-device-image-icon-or-cursor"></a>デバイスのイメージ (アイコンやカーソル) の作成します。

新しいアイコンやカーソルのリソースを作成するときに、**イメージ エディター**最初、特定のスタイル (32 × 32 の 16 色のアイコンと 32 × 32、カーソルのモノクロ) でイメージを作成します。 初期のアイコンやカーソルをさまざまなサイズとスタイルのイメージを追加し、必要に応じて、別のディスプレイ デバイスの各追加のイメージを編集できます。 既存のイメージの種類やグラフィックス プログラムで作成したビットマップからカット アンド ペースト操作を使用してイメージを編集することもできます。

アイコンまたはカーソルのリソースを開くと、[イメージ エディター](../windows/image-editor-for-icons.md)、密接に現在のディスプレイ デバイスを照合ほとんどが既定で表示するイメージ。

> [!NOTE]
> 場合は、プロジェクトに .rc ファイル含まれていないを参照してください。[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)です。

**新規&lt;デバイス&gt;イメージの種類** ダイアログ ボックスでは、指定した型の新しいデバイス イメージを作成することができます。 開くには、**新規\<デバイス > イメージ**メニューに移動 ダイアログ ボックスで、**イメージ** > **イメージ タイプの新規**します。 次のプロパティが含まれている**ターゲット イメージ タイプ**と**カスタム**します。

**ターゲット イメージ タイプ**プロパティ、イメージを選択した使用可能なイメージの種類の一覧を開きたい型。

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

**カスタム**プロパティが表示されます、**カスタム イメージ**ダイアログ ボックスでカスタムのサイズと色の数を新しいイメージを作成できます。

**カスタム イメージ** ダイアログ ボックスでは、カスタムのサイズと色の数で新しいイメージを作成することができます。 次のプロパティは次のとおりです。

|プロパティ|説明|
|---|---|
|**Width**|カスタム イメージの幅をピクセル (1 ~ 512 の制限を 2048) で入力する場所を提供します。|
|**Height**|ピクセル (1 ~ 512 の制限を 2048) でカスタム イメージの高さを入力する場所を提供します。|
|**色**|カスタム イメージの色の数を選択する場所を提供します。2、16、または 256 です。|

使用して、**開く&lt;デバイス&gt;イメージ**を C++ プロジェクトでデバイスのイメージを開く ダイアログ ボックス。 現在のリソース (現在のリソースの一部であるイメージ) の既存のデバイスのイメージが一覧表示します。 次のプロパティは次のとおりです。

|プロパティ|説明|
|---|---|
|**現在のイメージ**|リソースに含まれるイメージを一覧表示します。 開きたい画像の種類を選択します。|

#### <a name="to-create-a-new-icon-or-cursor"></a>新しいアイコンやカーソルを作成するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)を右クリックし、 *.rc*ファイルを選択し、**リソースの挿入**します。 既存のイメージ リソースが既にある場合、 *.rc*ファイルを右クリックしてなど、カーソル、**カーソル**フォルダーと選択**挿入カーソル**します。

1. [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)を選択します**アイコン**または**カーソル**選択**新規**します。 アイコンには、この操作は、32 × 32、16 色のアイコンのアイコン リソースを作成します。 カーソルの場合は 32 × 32、モノクロの (2 色) イメージが作成されます。

   プラス記号の場合 (**+**) でイメージ リソースの種類の横に表示、**リソースの挿入**ダイアログ ボックスで、ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択して、選択、プラス記号を選択します。**新規**します。

### <a name="to-add-an-image-for-a-different-display-device"></a>別のディスプレイ デバイスのイメージを追加するには

1. メニューに移動して**イメージ** > **新しいデバイス イメージ**、またはで右クリック、**イメージ エディター**ウィンドウ選択**新しいデバイス イメージ**。

1. 追加するイメージの種類を選択します。 選択することも**カスタム**サイズが既定の一覧では使用できません。 アイコンを作成します。

### <a name="to-copy-a-device-image"></a>デバイス イメージをコピーするには

1. メニューに移動して**イメージ** > **デバイス イメージを開いて**と現在のイメージ リストからイメージを選択します。 たとえば、32 × 32 の 16 色のバージョンのアイコンを選択します。

1. 現在表示されているアイコンのイメージのコピー (**Ctrl**+**C**)。

1. 別のアイコンの別のイメージを開く**イメージ エディター**ウィンドウ。 たとえば、16 × 16 の 16 色のバージョンのアイコンを開きます。

1. アイコン イメージを貼り付けます (**Ctrl**+**V**) から 1 つ**イメージ エディター**他のウィンドウ。 小さいサイズに大きなサイズのデータを貼り付ける場合は、イメージのサイズを変更するアイコンのハンドルを使用できます。

### <a name="to-delete-a-device-image"></a>デバイス イメージを削除するには

アイコン画像が表示されますが、**イメージ エディター**メニューに移動して、**イメージ** > **デバイス イメージの削除**します。 リソースの最後のアイコン イメージを削除すると、リソースも削除されます。

> [!NOTE]
> 押したときに、 **Del**イメージとアイコンを描画する色キーを削除一方、アイコンは残っており、今すぐ再設計できることです。 キーを押す場合**Del**を誤ってキーを押して**Ctrl**+**Z**アクションを元に戻す。

### <a name="to-create-transparent-or-inverse-regions-in-device-images"></a>デバイス イメージの透明または反転領域を作成するには

[イメージ エディター](../windows/image-editor-for-icons.md)、初期のアイコンまたはカーソルのイメージが透明な属性。 アイコンとカーソルのイメージは四角形が、多くのでは表示されません、イメージの部分は透過的であり、アイコンまたはカーソルを画面上の基になるイメージを示しています。 アイコンをドラッグするときに、反転色でイメージの部分を引き起こすことがあります。 画面の色との逆の色を設定してこの効果を作成する、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。

画面と反転色のアイコンに適用して、カーソルか図形し色の派生イメージまたは反転領域の割り当ています。 色は、これらの属性を持つイメージの部分を表します。 編集画面の色と反転色の属性を表す色を変更することができます。 これらの変更は、アイコンやカーソルをアプリケーションの外観に影響はありません。

> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、**ヘルプ**の説明と異なる場合があります。 設定を変更するには、メニューに移動**ツール** > **インポートおよびエクスポート設定**します。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

#### <a name="to-create-transparent-or-inverse-regions"></a>透明または反転領域を作成するには

1. **色**ウィンドウで、セレクターを選択**画面の色**または**反転色**します。

1. 画面描画ツールを使用して、イメージに逆の色を適用します。 描画ツールの詳細については、次を参照してください。[描画ツールを使用して](using-a-drawing-tool-image-editor-for-icons.md)します。

#### <a name="to-change-the-screen-or-inverse-color"></a>画面または反転色を変更するには

1. いずれかを選択、**画面の色**セレクターまたは**反転色**セレクター。

1. 色を選択、**色**パレットで、**色**ウィンドウ。

   補色は他のセレクターを自動的に割り当てられます。

   > [!TIP]
   > ダブルクリックする場合、**画面の色**または**反転色**セレクター、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)が表示されます。

### <a name="use-the-256-color-palette"></a>256 色カラー パレットを使用します。

使用して、**イメージ エディター**アイコンとカーソルからのサイズが設定された大きな (64 × 64) 256 色カラー パレットを選択するとを指定できます。 リソースを作成すると、デバイスのイメージのスタイルが選択されます。

#### <a name="to-create-a-256-color-icon-or-cursor"></a>256 色のアイコンまたはカーソルを作成するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)を右クリックし、 *.rc*ファイルを選択し、**リソースの挿入**します。 既存のイメージ リソースが既にある場合、 *.rc*ファイルを右クリックしてなど、カーソル、**カーソル**フォルダーと選択**挿入カーソル**します。

1. [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)を選択します**アイコン**または**カーソル**選択**新規**します。

1. メニューに移動して**イメージ** > **新しいデバイス イメージ**256 色の画像のスタイルを選択します。

#### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>大きいアイコンの 256 色カラー パレットから色を選択するには

256 色カラー パレットから選択した場合、描画するから色を選択する必要があります、**色**パレットで、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。

1. 大きいアイコンまたはカーソルを選択するか、新しいの大きいアイコンまたはカーソルを作成します。

1. 色で表示される 256 色から選択、**色**パレットで、**色**ウィンドウ。

   選択した色に現在の色になります、**色**パレットで、**色**ウィンドウ。

   > [!NOTE]
   > 256 色の画像に使用する初期のパレットがによって返されるパレットと一致する、 `CreateHalftonePalette` Windows API。 Windows シェルは、すべてのアイコンは、パレットの実現化中のちらつきを防ぐためにこのパレットを使用する必要があります。

### <a name="to-set-a-cursors-hot-spot"></a>カーソルのホット スポットを設定するには

カーソルのホット スポットとは、ポイントにカーソルの位置を追跡することで Windows を参照します。 既定では、ホット スポットは、カーソルの座標での左上隅に設定`0,0`します。 **ホット スポット**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)ホット スポットの座標を示します。

1. [イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)、選択、**ホット スポットの設定**ツール。

1. カーソルのホット スポットとして指定するピクセルを選択します。

   **ホット スポット**プロパティ、**プロパティ**ウィンドウには、新しい座標が表示されます。

### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>作成し、.jpeg、.gif としてビットマップを保存するには

ビットマップを作成するときに、イメージはビットマップ (.bmp) の形式で作成されます。 ただし、他のグラフィック形式または gif 形式や JPEG としてイメージを保存することができます。

> [!NOTE]
> アイコンとカーソルには、このプロセスは適用されません。

1. メニューに移動して**ファイル** > **オープン**を選択し、**ファイル**します。

1. **新しいファイル ダイアログ ボックス**、選択、 **Visual C**フォルダーを選択し、**ビットマップ ファイル (.bmp)** で、**テンプレート**ボックスし、を選択します。**開いている**します。

   ビットマップが開きます、**イメージ エディター**します。

1. 必要に応じて、新しいビットマップを変更を加えます。

1. ビットマップで開いたままで、**イメージ エディター**メニューに移動して、**ファイル** > **保存*filename*として .bmp**します。

1. **ファイルに名前を付けて** ダイアログ ボックスに、ファイルとファイル形式で目的を示す拡張機能を提供する名前を入力、**ファイル名**ボックス。 たとえば、 *myfile.gif*します。

   > [!NOTE]
   > 構成データベースを作成するか、別のファイル形式として保存するには、プロジェクトの外部のビットマップを開きます。 作成するか、プロジェクト内で開いて、**付けて**コマンドは使用できません。 詳細については、次を参照してください。[を表示するリソースで、リソース スクリプト ファイル プロジェクトの外側 (スタンドアロン)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

1. **[保存]** を選択します。

### <a name="to-convert-an-image-from-one-format-to-another"></a>イメージを別の 1 つの形式に変換するには

Gif 形式や JPEG イメージを開くことができます、**イメージ エディター**ビットマップとして保存します。 また、ビットマップ ファイルを開くし、gif 形式や JPEG として保存できます。 使用するイメージで開発環境で編集するためのプロジェクトの一部必要はありません (を参照してください[スタンドアロン画像編集](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md))。

1. 内のイメージを開く、**イメージ エディター**します。

1. メニューに移動して**ファイル** > **保存*filename*として**します。

1. **ファイルに名前を付けて** ダイアログ ボックスで、**ファイル名**ボックスに、ファイル名と必要な形式を示す拡張子を入力します。

1. **[保存]** を選択します。

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>アンマネージの C++ プロジェクトに新しいイメージ リソースを追加するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)を右クリックし、 *.rc*ファイルを選択し、**リソースの挿入**します。 既存のイメージ リソースが既にある場合、 *.rc*ファイルなど、カーソルを単に右クリック、**カーソル**フォルダーと選択**挿入カーソル**します。

1. [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)、作成するには、イメージ リソースの種類を選択します (**ビットマップ**など) を選択し、**新規**。

   プラス記号の場合 (**+**) でイメージ リソースの種類の横に表示、**リソースの挿入**ダイアログ ボックスで、ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択して、選択、プラス記号を選択します。**新規**します。

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>.NET のプログラミング言語のプロジェクトに新しいイメージ リソースを追加するには

1. **ソリューション エクスプ ローラー**、プロジェクト フォルダーを右クリックし (たとえば、 *WindowsApplication1*)。

1. ショートカット メニューでは、次のように選択します。**追加**、を選択し、**新しい項目の追加**します。

1. **カテゴリ**ウィンドウで、展開、**ローカル プロジェクト アイテム**フォルダーを選択し、**リソース**します。

1. **テンプレート**ウィンドウで、プロジェクトに追加するには、リソースの種類を選択します。

   プロジェクトにリソースを追加**ソリューション エクスプ ローラー**され、リソースがで、[イメージ エディター](../windows/image-editor-for-icons.md)します。 使用できるすべてのツールを使用できるようになりました、**イメージ エディター**イメージを変更します。 マネージ プロジェクトにイメージを追加する方法の詳細については、次を参照してください。[デザイン時にピクチャの読み込み](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)<br/>
[方法: 画像を編集する](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[方法: 描画ツールを使用する](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[方法: 色を調整する](../windows/working-with-color-image-editor-for-icons.md)<br/>
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
<!--
[Converting Bitmaps to Toolbars](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Creating New Toolbars](../windows/creating-new-toolbars.md)<br/>
[Icons](/windows/desktop/menurc/icons)<br/>
[Cursors](/windows/desktop/menurc/cursors)<br/>-->