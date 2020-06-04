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
ms.openlocfilehash: b0041124c35414a0c1c998642b5321319602c872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359853"
---
# <a name="how-to-use-a-drawing-tool"></a>方法: 描画ツールを使用する

**イメージ エディター**には、すべて同じように機能するフリーハンドの描画ツールとツールの一覧が表示されます。 ツールを選択し、必要に応じて[、前景色と背景色、](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)サイズと形状のオプションを選択します。 次に、ポインタを画像に移動し、クリックまたはドラッグして描画および消去します。

## <a name="drawing-tools"></a>描画ツール

描画ツールは、[**イメージ エディタ]** ツールバーまたは [**イメージ**] メニューから選択できます。 **消しゴム**ツール、**ブラシ**ツール、または**エアブラシ**ツールを選択すると、オプションセレクターにそのツールのオプションが表示されます。

> [!TIP]
> [イメージ エディターのツール バー](../windows/toolbar-image-editor-for-icons.md)のボタンにカーソルを合わせると、ツール ヒントが表示されます。 これらのヒントは、ここで説明する特定のボタンを識別するのに役立ちます。

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>[イメージ エディター] ツールバーから描画ツールを選択して使用するには

1. **[イメージ エディター** ] ツールバーのボタンを選択します。

   - マウスの左ボタンを押すと、**消しゴム**ツールが現在の背景色でイメージの上にペイントします。

      > [!TIP]
      > **消しゴム**ツールを使用する代わりに、描画ツールの 1 つで背景色を描画する方が便利な場合があります。

   - **鉛筆**ツールは、1 ピクセルの一定の幅でフリーハンドを描画します。

   - **ブラシ**ツールには、さまざまな形状とサイズがあります。

   - **エアブラシ**ツールは、ブラシの中心を中心にカラーピクセルをランダムに分配します。

1. 必要に応じて、色とブラシを選択します。

   - カラー[パレット](../windows/colors-window-image-editor-for-icons.md)で、マウスの左ボタンを選択して前景色を選択するか、マウスの右ボタンをクリックして背景色を選択します。

   - [[オプション] セレクター](../windows/toolbar-image-editor-for-icons.md)で、使用するブラシを表す図形を選択します。

1. 描画またはペイントを開始するイメージ上の場所をポイントします。 選択したツールに応じて、ポインタの形状が変化します。

1. マウスの左ボタン (前景色の場合) またはマウスの右ボタン (背景色の場合) を押し、描画時に押し続けます。

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>[イメージ] メニューから描画ツールを選択して使用するには

1. メニュー**イメージ** > **ツールに**移動します。

1. カスケード サブメニューで、使用するツールを選択します。

## <a name="lines-or-closed-figures"></a>線または閉じた図形

線や閉じた図形を描画する**イメージ エディタ**ツールは、カーソルを 1 つのポイントに置き、別のポイントにドラッグします。 線分の場合、これらの点は端点です。 閉じた図形の場合、これらの点は図形に外接する四角形の角の反対側にあります。

線は現在のブラシ選択によって決まる幅で描画され、フレーム化された図形は現在の幅選択によって決まる幅で描画されます。 線とすべての図形は、フレームと塗りつぶしの両方で、マウスの左ボタンを押すと現在の前景色、またはマウスの右ボタンを押すと現在の背景色で描画されます。

### <a name="to-draw-a-line"></a>線を描画するには

1. [[イメージ エディター](../windows/toolbar-image-editor-for-icons.md) ] ツールバーを使用するか、メニュー**の [イメージ**> **ツール]** に移動して **[線]** ツールを選択します。

1. 必要に応じて、色とブラシを選択します。

   - カラー[パレット](../windows/colors-window-image-editor-for-icons.md)で、マウスの左ボタンを選択して前景色を選択するか、マウスの右ボタンをクリックして背景色を選択します。

   - [[オプション] セレクター](../windows/toolbar-image-editor-for-icons.md)で、使用するブラシを表す図形を選択します。

1. 線の始点にポインタを置きます。

1. 線の端点までドラッグします。

### <a name="to-draw-a-closed-figure"></a>閉じた図形を描画するには

1. **[イメージ エディター** ] ツールバーを使用するか、メニューの **[イメージ** > **ツール]** に移動して **、閉じた図形描画**ツールを選択します。

   **クローズドフィギュア描画**ツールは、それぞれのボタンに示すように図形を作成します。

1. 必要に応じて、色と線幅を選択します。

1. 図形を描画する四角形領域の 1 つのコーナーにポインタを移動します。

1. ポインタを斜め反対側のコーナーにドラッグします。

## <a name="custom-brushes"></a>カスタムブラシ

カスタム ブラシは、イメージ エディターの既製ブラシの 1 つのように、選択して使用する**イメージ**の四角形の部分です。 選択に対して実行できるすべての操作は、カスタム ブラシでも実行できます。

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>イメージの一部からカスタム ブラシを作成するには

1. ブラシに使用するイメージの部分を選択します。

1. Shift**キーを押**しながら選択した項目を選択してイメージ上でドラッグするか、メニュー **[イメージ** > **使用ブラシ**] に移動します。

   選択したブラシは、選択した色をイメージ全体に分散するカスタム ブラシになります。 選択範囲のコピーは、ドラッグパスに沿って左に表示されます。 ドラッグが遅いほど、より多くのコピーが作成されます。

   > [!NOTE]
   > 最初にイメージの一部を選択せずに **[選択をブラシとして使用**]を選択すると、イメージ全体がブラシとして使用されます。 カスタム ブラシを使用した結果は、選択した背景が[[不透明] か [透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)] のどちらであるかによっても異なります。

現在の背景色に一致するカスタム ブラシのピクセルは、通常は透明で、既存のイメージの上にペイントされません。 この動作を変更して、背景色のピクセルが既存のイメージの上にペイントされるようにすることができます。

スタンプやステンシルなどのカスタム ブラシを使用して、さまざまな特殊効果を作成できます。

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>カスタム ブラシ図形を背景色で描画するには

1. 不透明または透明な背景を選択します。

1. 描画する色に背景色を設定します。

1. 描画する位置にカスタム ブラシを配置します。

1. マウスの右ボタンを選択します。 カスタム ブラシの不透明な領域は背景色で描画されます。

### <a name="to-double-or-halve-the-custom-brush-size"></a>カスタム ブラシ サイズを 2 倍または半分にするには

**プラス記号**()**+** キーを押してブラシのサイズを 2 倍**-** にするか、**マイナス記号**() キーを押して半分にします。

### <a name="to-cancel-the-custom-brush"></a>カスタム ブラシをキャンセルするには

**Esc キーを押**すか、別の描画ツールを選択してください。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)<br/>
[方法 : アイコンまたはその他のイメージを作成する](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[方法 : イメージを編集する](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[方法 : 色を操作する](../windows/working-with-color-image-editor-for-icons.md)<br/>
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
