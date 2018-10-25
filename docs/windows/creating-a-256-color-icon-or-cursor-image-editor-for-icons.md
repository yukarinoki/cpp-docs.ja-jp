---
title: 256 色のアイコンまたはカーソル (アイコン用イメージ エディター) の作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dcd9edb155afa9138778f1d464a5e59a20dd7ffd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070032"
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>256 色のアイコンまたはカーソルの作成 (アイコン用イメージ エディター)

使用して、**イメージ**エディター、アイコンとカーソルは、サイズが設定された大きな (64 × 64) 256 色カラー パレットから選択するとします。 リソースを作成すると、デバイスのイメージのスタイルが選択されます。

### <a name="to-create-a-256-color-icon-or-cursor"></a>256 色のアイコンまたはカーソルを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし**リソースの挿入**ショートカット メニューからです。 (を単に右クリックなど、カーソル、.rc ファイルに既存のイメージ リソースが既にある場合、**カーソル**フォルダーと選択**挿入カーソル**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. [リソースの挿入ダイアログ ボックス](../windows/add-resource-dialog-box.md)[**アイコン**または**カーソル**] をクリック**新規**です。

3. **イメージ** メニューのをクリックして**新しいデバイス イメージ**します。

4. 256 色の画像のスタイルを選択します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[256 色カラー パレットの使用](../windows/using-the-256-color-palette-image-editor-for-icons.md)<br/>
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)