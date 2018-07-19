---
title: デバイス イメージ (アイコン用イメージ エディター) の透過的または反転領域の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], screen regions
- inverse colors, device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices, transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects, transparent images
- icons [C++], screen regions
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 70fd2411eefba495478baaf5fb20fe7a27031001
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882551"
---
# <a name="creating-transparent-or-inverse-regions-in-device-images-image-editor-for-icons"></a>デバイス イメージの透明な領域または反転領域の作成 (アイコン用イメージ エディター)
[イメージ エディター](../windows/image-editor-for-icons.md)、初期のアイコンまたはカーソルのイメージが透明な属性です。 アイコンとカーソルのイメージは、四角形は、多くはために表示されないため、イメージの部分は透過的です。画面の基になるイメージは、アイコンやカーソルを示しています。 アイコンをドラッグするとき、反転色でイメージの部分を引き起こすことがあります。 画面の色との逆の色を設定してこの特殊効果を作成する、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。  
  
 画面と反転色のアイコンに適用してカーソル図形の色の派生のイメージか逆方向の領域を指定します。 色は、これらの属性を処理するイメージの部分を表します。 編集中の画面の色と反転色の属性を表す色を変更することができます。 これらの変更は、アイコンや、アプリケーションでのカーソルの外観には影響しません。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### <a name="to-create-transparent-or-inverse-regions"></a>透明または反転領域を作成するには  
  
1.  **色**ウィンドウで、をクリックして、**画面の色**セレクターまたは**反転色**セレクター。  
  
2.  画面描画ツールを使用して、イメージに逆の色を適用します。 描画ツールの詳細については、次を参照してください。[描画ツールを使用して](using-a-drawing-tool-image-editor-for-icons.md)です。  
  
### <a name="to-change-the-screen-or-inverse-color"></a>画面または反転色を変更するには  
  
1.  いずれかを選択、**画面の色**セレクターまたは**反転色**セレクター。  
  
2.  色を選択、**色**のパレット、**色**ウィンドウです。  
  
     その他のセレクターの補色が自動的に指定します。  
  
    > [!TIP]
    >  画面の色または反転色のセレクターをダブルクリックする場合、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)が表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

