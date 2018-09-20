---
title: 256 色カラー パレット (アイコン用イメージ エディター) を使用して |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- colors [C++], icons and cursors
- cursors [C++], color
- color palettes, 256-color
- palettes, 256-color
- icons, color
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d9a8952ccdf4477f263a2fb960020e7abba19546
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418152"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>256 色カラー パレットの使用 (アイコン用イメージ エディター)

256 色カラー パレットから選択した場合、描画するから色を選択する必要があります、**色**パレットで、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)します。

### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>大きいアイコンの 256 色カラー パレットから色を選択するには

1. 大きいアイコンまたはカーソルを選択するか、新しいの大きいアイコンまたはカーソルを作成します。

2. 色で表示される 256 色から選択、**色**パレットで、**色**ウィンドウ。

   選択した色に現在の色になります、**色**パレットで、**色**ウィンドウ。

   > [!NOTE]
   > 256 色の画像に使用する初期のパレットがによって返されるパレットと一致する、 `CreateHalftonePalette` Windows API。 Windows シェルは、すべてのアイコンは、パレットの実現化中のちらつきを防ぐためにこのパレットを使用する必要があります。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[256 色のアイコンまたはカーソルの作成](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)<br/>
[アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)