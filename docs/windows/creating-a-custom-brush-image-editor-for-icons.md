---
title: カスタム ブラシ (アイコン用イメージ エディター) の作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62e4cb9d6eebee4235db2bc38b2cd20935493b02
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607981"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>カスタム ブラシの作成 (アイコン用イメージ エディター)

カスタム ブラシは四角形の部分を取得しのいずれかのように使用するイメージの**イメージ**エディターの既製のブラシ。 選択範囲に対して実行できるすべての操作、カスタム ブラシも実行できます。

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>イメージの一部からカスタム ブラシを作成するには

1. [イメージの一部を選択します。](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)ブラシに使用します。

2. 保持している、 **Shift**キー ダウンし、選択範囲内をクリックし、イメージ間でドラッグします。

   \- または -

3. **イメージ**] メニューの [選択**ブラシとして使用して選択**します。

   選択内容では、画像の選択範囲の色を分散するカスタム ブラシになります。 ドラッグするパスに沿った選択範囲のコピーが残されます。 緩やかに変化をドラッグする、複数のコピーを作成します。

   > [!NOTE]
   > クリックすると、**選択範囲をブラシとして使用**をブラシとして全体のイメージを使用するイメージの一部をまず選択なし。 カスタム ブラシを使用しての結果は選択したかどうかに依存しても、[透明または不透明な背景](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)します。

現在の背景色に一致するカスタム ブラシのピクセルが透明な通常: 既存のイメージの上、描画はできません。 背景色のピクセルが既存のイメージを描画できるように、この動作を変更できます。

スタンプまたはステンシルなどのカスタム ブラシを使用して、さまざまな特殊効果を作成することができます。

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>背景色でカスタム ブラシの形状を描画するには

1. [非透過または透過の背景を選択して](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)します。

2. [背景色を設定](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)を描画する色にします。

3. 描画する位置にカスタム ブラシ。

4. マウスの右ボタンをクリックします。 カスタム ブラシの不透明な領域は、背景色で描画されます。

### <a name="to-double-or-halve-the-custom-brush-size"></a>ダブルクリックまたはカスタム ブラシのサイズの半分

1. キーを押して、**プラス**(**+**) ブラシのサイズを 2 倍にキーまたは**マイナス記号**(**-**) キーが半分にする.

### <a name="to-cancel-the-custom-brush"></a>カスタム ブラシをキャンセルするには

1. キーを押して**Esc**または別の描画ツールを選択します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)