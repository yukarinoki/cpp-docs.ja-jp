---
title: デバイス イメージ (アイコン用イメージ エディター) を作成する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 753971a7b010c8e3af1c36c56833a123c182a708
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318123"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>デバイス イメージの作成 (アイコン用イメージ エディター)

新しいアイコンやカーソルのリソースを作成するときに、**イメージ**エディターが特定のスタイル (32 × 32 の 16 色のアイコンと 32 × 32、カーソルのモノクロ) で最初にイメージを作成します。 初期のアイコンやカーソルをさまざまなサイズとスタイルのイメージを追加し、必要に応じて、別のディスプレイ デバイスの各追加のイメージを編集できます。 既存のイメージの種類やグラフィックス プログラムで作成したビットマップからカット アンド ペースト操作を実行することによってイメージを編集することもできます。

アイコンまたはカーソルのリソースを開くと、[イメージ エディター](../windows/image-editor-for-icons.md)、密接に現在のディスプレイ デバイスを照合ほとんどが既定で表示するイメージ。

### <a name="to-create-a-new-icon-or-cursor"></a>新しいアイコンやカーソルを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし**リソースの挿入**ショートカット メニューからです。 (を単に右クリックなど、カーソル、.rc ファイルに既存のイメージ リソースが既にある場合、**カーソル**フォルダーと選択**挿入カーソル**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. [リソースの挿入ダイアログ ボックス](../windows/add-resource-dialog-box.md)[**アイコン**または**カーソル**] をクリック**新規**です。 アイコン、これは、アイコン リソースを作成 32 × 32、16 色のアイコンとされます。 カーソルの場合は 32 × 32、モノクロの (2 色) イメージが作成されます。

   プラス記号の場合 (**+**) でイメージ リソースの種類の横に表示、**リソースの挿入**ダイアログ ボックスで、ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択してをクリックするには、プラス記号をクリックします。**新規**します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)