---
title: '方法: 描画ツールを使用する'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.drawing
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
- Image editor [C++], drawing lines
- shapes, drawing
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
ms.openlocfilehash: 61c06ee3fecac18fb95663c0d13474b8bd3b94f4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214384"
---
# <a name="how-to-use-a-drawing-tool"></a>方法: 描画ツールを使用する

**イメージエディター**には、すべて同じ方法で動作するツールが用意されています。 ツールを選択し、必要に応じて [[前景と背景の色] および [](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)サイズと形状] のオプションを選択します。 次に、ポインターをイメージに移動し、クリックまたはドラッグして描画と消去を行います。

## <a name="drawing-tools"></a>描画ツール

**イメージエディター** ツールバーまたは **イメージ** メニューから 描画ツール を選択できます。 **消しゴム**ツール、**ブラシ**ツール、または**エアブラシ**ツールを選択すると、オプションセレクターにそのツールのオプションが表示されます。

> [!TIP]
>  ツールヒントは、[[イメージエディター] ツールバー](../windows/toolbar-image-editor-for-icons.md)のボタンの上にカーソルを置くと表示されます。 これらのヒントは、ここで説明する特定のボタンを特定するのに役立ちます。

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>[イメージエディター] ツールバーから描画ツールを選択して使用するには

1. **[イメージエディター]** ツールバーのボタンを選択します。

   - **消しゴム**ツールは、マウスの左ボタンを押すと、イメージを現在の背景色で描画します。

      > [!TIP]
      > **消しゴム**ツールを使用する代わりに、描画ツールの1つを使用して背景色を描画する方が便利な場合があります。

   - **鉛筆**ツールは、1ピクセルの固定幅でフリーハンドを描画します。

   - **ブラシ**ツールには、さまざまな図形とサイズがあります。

   - **エア**ブラシツールでは、ブラシの中心を中心にカラーピクセルをランダムに分布します。

1. 必要に応じて、[色] と [ブラシ] を選択します。

   - [色パレット](../windows/colors-window-image-editor-for-icons.md)で、マウスの左ボタンを選択して前景色を選択するか、マウスの右ボタンをクリックして背景色を選択します。

   - [[オプション] セレクター](../windows/toolbar-image-editor-for-icons.md)で、使用するブラシを表す図形を選択します。

1. 描画または描画を開始するイメージ上の場所をポイントします。 選択したツールに応じて、ポインターの形状が変わります。

1. マウスの左ボタン (前景色の場合) またはマウスの右ボタン (背景色の場合) を押して、描画したままにします。

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>[イメージ] メニューから描画ツールを選択して使用するには

1. メニュー**イメージ** > **ツール**にアクセスします。

1. カスケードサブメニューで、使用するツールを選択します。

## <a name="lines-or-closed-figures"></a>線または閉じた図形

線と閉じた図形を描画するための**イメージエディター**ツールはすべて同じように動作します。1つのポイントに挿入ポイントを配置し、別のポイントにドラッグします。 行の場合、これらのポイントはエンドポイントです。 閉じた図形の場合、これらの点は、図を囲む四角形の反対側の角になります。

線は、現在のブラシの選択によって決められた幅で描画され、現在の幅の選択によって決まる幅で描画されます。 マウスの左ボタンを押すか、または現在の背景色でマウスの右ボタンを押すと、線とすべての図が、現在の前景色で描画されます。

### <a name="to-draw-a-line"></a>線を描画するには

1. [[イメージエディター] ツールバー](../windows/toolbar-image-editor-for-icons.md)を使用するか、[メニュー**イメージ**> **ツール**] をクリックして、 **[線]** ツールを選択します。

1. 必要に応じて、[色] と [ブラシ] を選択します。

   - [色パレット](../windows/colors-window-image-editor-for-icons.md)で、マウスの左ボタンを選択して前景色を選択するか、マウスの右ボタンをクリックして背景色を選択します。

   - [[オプション] セレクター](../windows/toolbar-image-editor-for-icons.md)で、使用するブラシを表す図形を選択します。

1. 行の開始位置にポインターを置きます。

1. を行のエンドポイントまでドラッグします。

### <a name="to-draw-a-closed-figure"></a>閉じた図形を描画するには

1. **[イメージエディター]** ツールバーを使用するか、[メニュー**イメージ** > **ツール**] にアクセスして、閉じた**図形の描画**ツールを選択します。

   **閉じた図形の描画**ツールは、それぞれのボタンに示されているとおりに図形を作成します。

1. 必要に応じて、[色] と [線の幅] を選択します。

1. 図形を描画する四角形の領域の1つの隅にポインターを移動します。

1. ポインターを斜めの反対隅にドラッグします。

## <a name="custom-brushes"></a>カスタムブラシ

カスタムブラシはイメージの四角形の部分であり、**イメージエディター**の既製のブラシのように選択して使用します。 選択に対して実行できるすべての操作は、カスタムブラシに対しても実行できます。

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>イメージの一部からカスタムブラシを作成するには

1. ブラシに使用するイメージの部分を選択します。

1. **Shift**キーを押しながら選択範囲を選択して画像全体にドラッグするか、メニュー**イメージ**に移動し**て選択項目をブラシとして使用** > ます。

   選択内容は、イメージ全体の選択範囲の色を分布するカスタムブラシになります。 選択範囲のコピーはドラッグパスに沿って残されます。 ドラッグした方が、より多くのコピーが作成されます。

   > [!NOTE]
   > [**選択範囲をブラシとして使用**する] を選択すると、最初に画像の一部を選択しなくても、画像全体がブラシとして使用されます。 カスタムブラシを使用した結果は、[不透明または透明な背景](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)を選択したかどうかによっても異なります。

現在の背景色に一致するカスタムブラシのピクセルは、通常は透明です。既存の画像には描画されません。 この動作を変更して、背景色のピクセルが既存のイメージに対して描画されるようにすることができます。

スタンプやステンシルなどのカスタムブラシを使用して、さまざまな特殊効果を作成できます。

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>背景色でカスタムブラシ図形を描画するには

1. 不透明または透明な背景を選択します。

1. 背景色を描画する色に設定します。

1. 描画するカスタムブラシを配置します。

1. マウスの右ボタンを選択します。 カスタムブラシの不透明な領域は、背景色で描画されます。

### <a name="to-double-or-halve-the-custom-brush-size"></a>カスタムブラシのサイズを2倍または半分にするには

**プラス記号**( **+** ) キーを押してブラシのサイズを2つ、または**マイナス記号**( **-** ) キーを押して、それを半分にします。

### <a name="to-cancel-the-custom-brush"></a>カスタムブラシをキャンセルするには

**Esc**キーを押すか、別の描画ツールを選択します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>参照

[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)<br/>
[方法: アイコンまたはその他のイメージを作成する](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[方法: イメージを編集する](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[方法: 色を操作する](../windows/working-with-color-image-editor-for-icons.md)<br/>
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
