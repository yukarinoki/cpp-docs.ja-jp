---
title: 描画ツール (アイコン用イメージ エディター) の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.drawing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e7f1c678cc2f5c3595f1782f1bb3561ae90b86a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609950"
---
# <a name="using-a-drawing-tool-image-editor-for-icons"></a>描画ツールの使用 (アイコン用イメージ エディター)

**イメージ**エディターの手描きツールと同じ方法ですべての作業のツールを消去: ツールを選択して、必要に応じて、[前景色と背景色を選択します。](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)とサイズおよび図形オプション。 イメージにポインターを移動し、クリックしてまたはドラッグした描画、消去します。

選択すると、**消しゴム**ツール、**ブラシ**ツール、または**エアブラシ**ツール オプション セレクターがそのツールのオプションが表示されます。

> [!TIP]
> 使用する代わりに、**消しゴム**ツール、かもしれません描画ツールのいずれかの背景色で描画する方が便利です。

いずれかの描画ツールを選択することができます、**イメージ エディター**ツールバーまたは**イメージ**メニュー。

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>選択して、イメージ エディターのツールバーから描画ツールを使用するには

1. ボタンをクリックして、**イメージ エディター**ツールバー。

   - **消しゴム**ツール、マウスの左ボタンを押すと現在の背景色とイメージを描画します。

   - **鉛筆**ツールが 1 つのピクセルの固定幅でフリーハンドを描画します。

   - **オプション セレクターは、ブラシ ツールの形状とサイズを決定します。** します。

   - **エアブラシ**ツールは、ブラシの中心の色ピクセルをランダムに分散させます。

        > [!TIP]
        >  上のボタンの上にカーソルを置くと、ツール ヒントが表示されます、[イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)します。 これらのヒントを使用すると、ここで説明する特定のボタンを識別できます。

2. 必要に応じて、色とブラシを選択します。

   - [色パレット](../windows/colors-window-image-editor-for-icons.md)前景の色を選択するマウスの左ボタンまたは背景色を選択するマウスの右ボタンをクリックします。

   - [オプション セレクター](../windows/toolbar-image-editor-for-icons.md)、使用するブラシを表す図形をクリックします。

3. 描画を開始するイメージまたは描画上の場所をポイントします。 ポインターは、選択したツールに応じて図形を変更します。

4. (の前景色) マウスの左ボタンまたは (の背景色) で、マウスの右ボタンを押して、押したままにする描画します。

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>選択し、[イメージ] メニューから描画ツールを使用するには

1. をクリックして、**イメージ**メニュー選択し、**ツール**コマンド。

2. カスケード型のサブメニューを使用するツールを選択します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)  
[カラーを使用します。](../windows/working-with-color-image-editor-for-icons.md)