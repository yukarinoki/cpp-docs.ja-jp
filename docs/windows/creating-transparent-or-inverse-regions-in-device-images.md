---
title: デバイスのイメージ (アイコン用イメージ エディター) の透過的なまたは反転領域の作成 |Microsoft Docs
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
ms.openlocfilehash: f5ed2a88e8963bae06e33835f3982d8651445929
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599521"
---
# <a name="creating-transparent-or-inverse-regions-in-device-images-image-editor-for-icons"></a>デバイス イメージの透明な領域または反転領域の作成 (アイコン用イメージ エディター)

[イメージ エディター](../windows/image-editor-for-icons.md)、初期のアイコンまたはカーソルのイメージが透明な属性。 アイコンとカーソルのイメージは四角形が、多くはために表示されません、イメージの部分は透過的です。アイコンまたはカーソルを画面上の基になるイメージを示しています。 アイコンをドラッグするときに、反転色でイメージの部分を引き起こすことがあります。 画面の色との逆の色を設定してこの効果を作成する、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。

画面と反転色のアイコンに適用して、カーソル図形の色の派生イメージか逆領域を指定します。 色は、これらの属性を含むイメージの部分を表します。 編集画面の色と反転色の属性を表す色を変更することができます。 これらの変更は、アイコンまたはカーソルをアプリケーションの外観には影響しません。

> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、**ヘルプ**の説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。

### <a name="to-create-transparent-or-inverse-regions"></a>透明または反転領域を作成するには

1. **色**ウィンドウで、をクリックして、**画面の色**セレクターまたは**反転色**セレクター。

2. 画面描画ツールを使用して、イメージに逆の色を適用します。 描画ツールの詳細については、次を参照してください。[描画ツールを使用して](using-a-drawing-tool-image-editor-for-icons.md)します。

### <a name="to-change-the-screen-or-inverse-color"></a>画面または反転色を変更するには

1. いずれかを選択、**画面の色**セレクターまたは**反転色**セレクター。

2. 色を選択、**色**パレットで、**色**ウィンドウ。

   補色は自動的に他のセレクターを指定します。

   > [!TIP]
   > ダブルクリックする場合、**画面の色**または**反転色**セレクター、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)が表示されます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)