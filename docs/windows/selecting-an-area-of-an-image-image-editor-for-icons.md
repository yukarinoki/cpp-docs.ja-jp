---
title: '方法: イメージを編集する'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
- Image editor [C++], flipping and rotating images
- images [C++], flipping
- images [C++], rotating
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
- size [C++], images
- images [C++], cropping
- images [C++], extending
- Image editor [C++], cropping or extending images
- Image editor [C++], shrinking and stretching images
- images [C++], stretching
- images [C++], shrinking
- bitmaps [C++], shrinking
- bitmaps [C++], stretching
- Image editor [C++], editing images
- images [C++], editing
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
ms.openlocfilehash: ecfd69594c05c210743e0c22c804a4713a8229ef
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509633"
---
# <a name="how-to-edit-an-image"></a>方法: イメージを編集する

選択ツールを使用すると、切り取り、コピー、クリア、サイズ変更、反転、または移動するイメージの領域を定義できます。 **四角形選択**ツールを使用すると、イメージの四角形の領域を定義して選択できます。 **不規則選択**ツールを使用すると、切り取り、コピー、またはその他の操作のために選択する領域のフリーハンドアウトラインを描画できます。

> [!NOTE]
> [イメージエディターのツールバー](./image-editor-for-icons.md)に表示される**四角形の選択**と**不規則な選択**ツールを参照するか、**イメージエディター**ツールバーの各ボタンに関連付けられているツールヒントを表示します。

選択範囲からカスタムブラシを作成することもできます。 詳細については、「 [カスタムブラシの作成](./using-a-drawing-tool-image-editor-for-icons.md)」を参照してください。

## <a name="how-to"></a>操作方法

イメージを編集するには、次の方法を参照してください。

### <a name="to-select-an-image"></a>イメージを選択するには

1. [**イメージエディター** ] ツールバーを使用するか、[メニュー**イメージ**  >  **ツール**] にアクセスして、必要な選択ツールを選択します。

1. 挿入ポイントを、選択するイメージ領域の1つの隅に移動します。 カーソルが画像上にあるときに十字線が表示されます。

1. 挿入ポイントを、選択する領域の反対側の隅にドラッグします。 四角形は、どのピクセルが選択されるかを示します。 四角形内のすべてのピクセルは、四角形の下にあるものも含め、選択範囲に含まれます。

1. マウスのボタンを離します。 選択した領域が選択範囲の境界線で囲まれます。

#### <a name="to-select-an-entire-image"></a>イメージ全体を選択するには

現在の選択範囲外のイメージを選択します。 選択境界線がフォーカスを変更し、画像全体が再び含まれます。

### <a name="to-edit-parts-of-an-image"></a>イメージの一部を編集するには

選択 [範囲に](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)対して、画像全体を使用するか、一部だけを選択して、標準の編集操作 (切り取り、コピー、消去、移動) を実行できます。 **イメージエディター**では**windows クリップボード**が使用されるため、**イメージエディター**と windows 用の他のアプリケーションとの間でイメージを転送できます。

さらに、イメージ全体を含めるか、一部だけを含めるかにかかわらず、選択範囲のサイズを変更できます。

#### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>現在の選択範囲を切り取ってクリップボードに移動するには

メニューの [切り取り] を**編集**  >  **Cut**します。

#### <a name="to-copy-the-selection"></a>選択範囲をコピーするには

1. ポインターを選択境界内、またはサイズ変更ハンドル以外の任意の場所に配置します。

1. **Ctrl**キーを押しながら、選択範囲を新しい場所にドラッグします。 元の選択範囲の領域は変更されません。

1. 選択範囲を現在の場所のイメージにコピーするには、選択カーソルの外側を選択します。

#### <a name="to-paste-the-clipboard-contents-into-an-image"></a>クリップボードの内容をイメージに貼り付けるには

1. メニューにアクセスして、[貼り付け] を**編集**  >  **Paste**します。

   選択境界で囲まれたクリップボードの内容が、ペインの左上隅に表示されます。

1. 選択境界内にポインターを置き、イメージをイメージ上の目的の場所にドラッグします。

1. 画像を新しい場所に固定するには、選択境界の外側を選択します。

#### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>現在選択されている項目をクリップボードに移動せずに削除するには

メニューにアクセスして、[削除] を**編集**  >  **Delete**します。

   選択範囲の元の領域は、現在の背景色で塗りつぶされます。

> [!NOTE]
> [ **切り取り**]、[ **コピー**]、[ **貼り付け**]、および [ **削除** ] の各コマンドにアクセスするには、[ **リソースビュー** ] ウィンドウを右クリックします。

#### <a name="to-move-the-selection"></a>選択範囲を移動するには

1. ポインターを選択境界内、またはサイズ変更ハンドル以外の任意の場所に配置します。

1. 選択範囲を新しい場所にドラッグします。

1. イメージ内の選択範囲を新しい場所に固定するには、選択境界の外側を選択します。

選択項目を使用した描画の詳細については、「 [カスタムブラシの作成](./using-a-drawing-tool-image-editor-for-icons.md)」を参照してください。

### <a name="to-flip-an-image"></a>イメージを反転させるには

イメージを反転または回転させるには、元のミラーイメージを作成するか、イメージを反転させるか、または画像を右の90°に回転させます。

- イメージを水平方向に反転させるには (ミラーイメージ)、[メニュー**イメージ**を左右に反転] を表示  >  **Flip Horizontal**します。

- 画像を垂直方向に反転させるには (反転)、[メニュー**イメージ**フリップ] [縦] に移動  >  **Flip Vertical**します。

- 画像を90度回転させるには、[メニュー**イメージ**] [  >  **90 °回転**] に切り替えます。

   > [!NOTE]
   > これらのコマンドに対して [アクセラレータ (ショートカット) キー](../windows/accelerator-keys-image-editor-for-icons.md) を使用したり、ショートカットメニューからコマンドにアクセスしたりすることもできます (イメージ **エディター**でイメージの外側を選択します)。

### <a name="to-resize-an-image"></a>画像のサイズを変更するには

イメージのサイズ変更中のイメージ **エディター** の動作は、イメージ全体を [選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) したか、その一部だけを選択したかによって異なります。

選択範囲にイメージの一部だけが含まれている場合、 **イメージエディター** では、行またはピクセルの列を削除し、空いている領域に現在の背景色を入力することで、選択範囲を縮小します。 また、行またはピクセルの列を複製して選択範囲を広げることもできます。

イメージ全体が選択範囲に含まれている場合、イメージ **エディター** はイメージを縮小または拡大するか、トリミングして拡張します。

イメージのサイズ変更には、サイズ変更ハンドルと [プロパティウィンドウ](/visualstudio/ide/reference/properties-window)の2つのメカニズムがあります。 サイズ変更ハンドルをドラッグして、イメージの全体または一部のサイズを変更します。 ドラッグできるサイズ変更ハンドルは実線です。 白抜きのハンドルはドラッグできません。 [ **プロパティ** ] ウィンドウを使用すると、選択した部分ではなく、イメージ全体のサイズを変更できます。

![ビットマップのサイズ変更ハンドル](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")<br/>
サイズ変更ハンドル

> [!NOTE]
> [[グリッドの設定] ダイアログボックス](./image-editor-for-icons.md)で [**タイルグリッド**] オプションを選択した場合、サイズを変更すると、次のタイルグリッド線にスナップされます。 [ピクセル] **グリッド** オプションのみが選択されている場合 (既定の設定)、サイズを変更すると、次に使用可能なピクセルにスナップされます。

#### <a name="to-resize-an-entire-image-using-the-properties-window"></a>[プロパティ] ウィンドウを使用してイメージ全体のサイズを変更するには

1. プロパティを変更するイメージを開きます。

1. [プロパティウィンドウ](/visualstudio/ide/reference/properties-window)の [**幅**] ボックスと [**高さ**] ボックスに、必要な大きさを入力します。

   イメージのサイズを大きくすると、イメージ **エディター** によってイメージが右、下、または両方に拡張され、新しい領域が現在の背景色で塗りつぶされます。 画像が拡大されていません。

   イメージのサイズを小さくすると、イメージ **エディター** によってイメージが右端または下端にトリミングされます。

   > [!NOTE]
   > **幅**と**高さ**のプロパティを使用すると、部分的な選択範囲のサイズを変更するのではなく、イメージ全体のサイズだけを変更できます。

#### <a name="to-crop-or-extend-an-entire-image"></a>イメージ全体をトリミングまたは拡張するには

1. イメージ全体を選択します。

   イメージの一部が現在選択されていて、イメージ全体を選択する場合は、イメージ上の現在の選択境界の外側の任意の場所を選択します。

1. イメージが適切なサイズになるまで、サイズ変更ハンドルをドラッグします。

通常、 **イメージエディター** では、サイズ変更ハンドルを移動してサイズを変更すると、イメージがトリミングまたは拡大されます。 **Shift**キーを押しながらサイズ変更ハンドルを移動すると、イメージ**エディター**によってイメージが縮小または拡大されます。

#### <a name="to-shrink-or-stretch-an-entire-image"></a>イメージ全体を縮小または拡大するには

1. イメージ全体を選択します。

   イメージの一部が現在選択されていて、イメージ全体を選択する場合は、イメージ上の現在の選択境界の外側の任意の場所を選択します。

1. **Shift**キーを押したまま、イメージが適切なサイズになるまで、サイズ変更ハンドルをドラッグします。

#### <a name="to-shrink-or-stretch-part-of-an-image"></a>イメージの一部を縮小または拡大するには

1. 画像のサイズを変更する部分を選択します。 詳細については、「 [イメージの領域の選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)」を参照してください。

1. サイズ変更ハンドルのいずれかをドラッグして、選択範囲が適切なサイズになるまでドラッグします。

### <a name="to-edit-an-image-outside-of-a-project"></a>プロジェクト外のイメージを編集するには

イメージは、グラフィックスアプリケーションの場合と同様に、開発環境で開いたり編集したりすることができます。たとえば、ビットマップを開いて、スタンドアロンで編集することができます。 作業するイメージは、Visual Studio プロジェクトの一部である必要はありません。

1. [メニュー**ファイル**を開く] にジャンプ  >  **Open**します。

1. [ **ファイルの種類** ] ボックスで、[ **すべてのファイル**] を選択します。

1. 編集するイメージを見つけて開きます。

### <a name="to-change-image-properties"></a>イメージのプロパティを変更するには

[プロパティウィンドウ](/visualstudio/ide/reference/properties-window)を使用して、イメージのプロパティを設定または変更できます。

1. イメージ **エディター**でイメージを開きます。

1. [ **プロパティ** ] ウィンドウで、イメージのすべてまたはすべてのプロパティを変更します。

   |プロパティ|説明|
   |--------------|-----------------|
   |**色**|画像の配色を指定します。 **モノクロ**、 **16**、または**256**、または**True の色**を選択します。<br/><br/>16色のパレットを使用してイメージを既に描画している場合は、[ **モノクロ** ] を選択すると、イメージ内の色に対して黒と白が置換されます。 コントラストは常に維持されません。たとえば、赤と緑の隣接する領域は両方とも黒に変換されます。|
   |**Filename**|画像ファイルの名前を指定します。<br/><br/>既定では、Visual Studio は、既定のリソース識別子 (IDB_BITMAP1) から最初の4文字 ("IDB_") を削除し、適切な拡張子を追加することによって作成された基本ファイル名を割り当てます。 この例では、イメージのファイル名は *BITMAP1.bmp*になります。 名前を *MYBITMAP1.bmp*に変更できます。|
   |**Height**|イメージの高さをピクセル単位で設定します。 既定値は48です。<br/><br/>画像がトリミングされているか、既存のイメージの下に空白が追加されています。|
   |**ID**|リソースの識別子を設定します。<br/><br/>イメージの場合、Microsoft Visual Studio は、既定では、IDB_BITMAP1、IDB_BITMAP2 などの次に使用可能な識別子を系列に割り当てます。 類似した名前がアイコンおよびカーソルに使用されます。|
   |**[パレット]**|色のプロパティを変更します。<br/><br/>ダブルクリックして色を選択し、[ [カスタムカラーセレクター] ダイアログボックス](./image-editor-for-icons.md)を表示します。 適切なテキストボックスに「RGB 値または HSL 値」と入力して色を定義します。|
   |**SaveCompressed れた**|画像が圧縮形式かどうかを示します。 このプロパティは読み取り専用です。<br/><br/>Visual Studio では、イメージを圧縮形式で保存することはできないため、Visual Studio で作成されたイメージでは、このプロパティは **False**になります。 (別のプログラムで作成された) 圧縮イメージを Visual Studio で開くと、このプロパティは **True**になります。 Visual Studio を使用して圧縮されたイメージを保存すると、圧縮が解除され、このプロパティは **False**に戻ります。|
   |**Width**|イメージの幅をピクセル単位で設定します。 ビットマップの既定値は48です。<br/><br/>画像がトリミングされるか、既存のイメージの右側に空白が追加されます。|

## <a name="requirements"></a>必要条件

None

## <a name="see-also"></a>関連項目

[アイコン用イメージエディター](../windows/image-editor-for-icons.md)<br/>
[方法: アイコンまたはその他のイメージを作成する](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[方法: 描画ツールを使用する](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[方法: 色を操作する](../windows/working-with-color-image-editor-for-icons.md)<br/>
[アクセラレータキー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
