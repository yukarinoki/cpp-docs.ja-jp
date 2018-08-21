---
title: 線または閉じた図形 (アイコン用イメージ エディター) の描画 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- closed figures, drawing
- lines [C++], painting
- lines [C++], drawing
- Image editor [C++], drawing lines
- shapes, drawing
ms.assetid: 7edd86db-77b1-451f-8001-bbfed9c6304f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ca853e5dd44cd91edbae99cc51f88a41bdd4130
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648377"
---
# <a name="drawing-lines-or-closed-figures-image-editor-for-icons"></a>線または閉じた図形の描画 (アイコン用イメージ エディター)
線を描画用イメージ エディターのツールし、同じ方法で作業できるすべての閉じた図形。 1 つのポイントにカーソルを配置し、別にドラッグします。 線、これらのポイントは、エンドポイントが。 閉じた図形は、これらのポイントは、図を囲む四角形の反対側の角です。  
  
 現在のブラシの選択によって決定幅で線が描画され、枠付きの図形が幅の現在の選択範囲によって決まります幅で描画されます。 マウスの右ボタンを押した場合、行およびとフレームの両方でいっぱいになったすべての図形が現在の前景の色をマウスの左ボタンを押した場合のまたは現在の背景色でを描画します。  
  
### <a name="to-draw-a-line"></a>線を描画するには  
  
1.  [イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md) (または、**イメージ**] メニューの [**ツール**コマンド)、をクリックして、**行**ツール。  
  
2.  必要に応じて、色とブラシを選択します。  
  
    -   [色パレット](../windows/colors-window-image-editor-for-icons.md)前景の色を選択するマウスの左ボタンまたは背景色を選択するマウスの右ボタンをクリックします。  
  
    -   [オプション セレクター](../windows/toolbar-image-editor-for-icons.md)、使用するブラシを表す図形をクリックします。  
  
3.  線の開始位置にポインターを置きます。  
  
4.  線の終点をドラッグします。  
  
### <a name="to-draw-a-closed-figure"></a>閉じた図を描画するには  
  
1.  **イメージ エディター**ツールバー (または、**イメージ**] メニューの [**ツール**コマンド)、をクリックして、**図形**ツール。  
  
     **図形**ツールは、各ボタンに記載のとおりに図形を作成します。  
  
2.  必要に応じて、色と線の幅を選択します。  
  
3.  図を描画する四角形の領域の 1 つ上の隅にポインターを移動します。  
  
4.  対角にポインターをドラッグします。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)   
 [カラーを使用します。](../windows/working-with-color-image-editor-for-icons.md)