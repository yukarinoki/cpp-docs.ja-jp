---
title: カスタム ブラシ (アイコン用イメージ エディター) の作成 |Microsoft ドキュメント
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
ms.openlocfilehash: a879850c00957568065150b6c6fc1c801c049fa2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873148"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>カスタム ブラシの作成 (アイコン用イメージ エディター)
カスタム ブラシは、四角形を取得し、イメージ エディターの既製のブラシのいずれかのように使用するイメージの一部です。 な選択で実行できる操作はすべて、カスタム ブラシも実行できます。  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>イメージの部分からカスタム ブラシを作成するには  
  
1.  [イメージの一部を選択して](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)ブラシに使用します。  
  
2.  保持している、 **shift キーを押し**キー ダウン、選択範囲で をクリックして、および画像をドラッグします。  
  
     \- または -  
  
3.  **イメージ**] メニューの [選択**ブラシとして使用する選択**です。  
  
     選択内容では、画像内で選択されている色を分散するカスタム ブラシになります。 選択範囲のコピーは、ドラッグするパスに沿った残されます。 ドラッグするより緩やかに変化は、複数のコピーが行われます。  
  
     **注**をクリックすると、**選択範囲を使用して、ブラシとして**ブラシとして全体のイメージを使用する最初のイメージの部分を選択することがなくです。 カスタム ブラシを使用しての結果も異なります選択するか、[透明または不透明な背景](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)です。  
  
 カスタム ブラシの現在の背景色に一致するピクセルは通常透過的: 既存のイメージをペイントはありません。 背景色のピクセルが既存のイメージの上に描画できるように、この動作を変更できます。  
  
 スタンプまたはステンシルなどのカスタム ブラシを使用すると、さまざまな特殊効果を作成します。  
  
#### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>背景色でカスタム ブラシの形状を描画するには  
  
1.  [非透過または透過の背景を選択](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)です。  
  
2.  [背景色を設定](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)を描画する色にします。  
  
3.  描画する位置にカスタム ブラシ。  
  
4.  マウスの右ボタンをクリックします。 カスタム ブラシの不透明な領域は、背景色で描画されます。  
  
#### <a name="to-double-or-halve-the-custom-brush-size"></a>ダブルクリックまたはカスタム ブラシのサイズを半分に  
  
1.  キーを押して、**プラス記号**(**+**) ブラシのサイズを 2 倍にするキーまたは**マイナス記号**(**-**) それを半分にするキー.  
  
#### <a name="to-cancel-the-custom-brush"></a>カスタム ブラシをキャンセルするには  
  
1.  キーを押して**ESC**か、別の描画ツールを選択します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

