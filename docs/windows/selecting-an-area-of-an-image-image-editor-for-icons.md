---
title: イメージの領域の選択 (アイコン用イメージ エディター)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
ms.openlocfilehash: 5e2522d23b30a91639e887a8761871e3df8139f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565114"
---
# <a name="selecting-an-area-of-an-image-image-editor-for-icons"></a>イメージの領域の選択 (アイコン用イメージ エディター)

選択内容 ツールを使用すると、切り取り、コピー、クリア、サイズを変更、反転、または移動するイメージの領域を定義します。 **矩形選択**ツールを定義し、イメージの四角形の領域を選択します。 **不規則選択**ツール、切り取り、コピー、またはその他の操作を選択する領域のフリーハンドのアウトラインを描画できます。

> [!NOTE]
> 参照してください、**矩形選択**と**不規則選択**ツールには描か[イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md) の各ボタンに関連付けられたツールヒントを表示または**イメージ エディター**ツールバー。

選択範囲からカスタム ブラシを作成することもできます。 詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。

### <a name="to-select-an-area-of-an-image"></a>イメージの領域を選択するには

1. **イメージ エディター**ツールバー (または、**イメージ**] メニューの [**ツール**コマンド)、必要なツールを選択します。

2. 選択したいイメージ領域の 1 つ上の隅にカーソルを移動します。 十字線は、カーソルが画像の上にあると表示されます。

3. 挿入ポイントを選択する領域の反対側の隅にドラッグします。 四角形に表示するピクセルが選択されます。 四角形の下にあるものを含む四角形内のすべてのピクセルは、選択範囲に含まれます。

4. マウスのボタンを離します。 選択範囲の境界線は、選択した領域を囲みます。

### <a name="to-select-an-entire-image"></a>イメージ全体を選択するには

1. 現在の選択範囲の外部で画像をクリックします。 選択範囲の境界線は、フォーカスを変更し、もう一度画像全体が含まれます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)