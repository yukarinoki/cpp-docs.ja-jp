---
title: 'アイコンとカーソル: ディスプレイ デバイス (アイコン用イメージ エディター) のイメージ リソース |Microsoft ドキュメント'
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
- image resources, display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices, creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a977629cbae140afa1463a7765f193a7519e1f68
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881911"
---
# <a name="icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons"></a>アイコンとカーソル: ディスプレイ デバイスのイメージ リソース (アイコン用イメージ エディター)
アイコンとカーソルは、グラフィカルなリソースで、表示デバイスの種類ごとに異なるサイズや色スキームの複数のイメージを含めることができます。 さらに、カーソルには「ホット スポット」があります。これは、その位置を追跡するために Windows で使用されるロケーションです。 アイコンとカーソルのどちらも、ビットマップやその他のイメージと同様、イメージ エディターを使用して作成および編集されます。  
  
 新しいアイコンやカーソルを作成する際、イメージ エディターはまず、標準タイプのイメージを作成します。 イメージは最初、画面の色 (透明) で塗られます。 イメージがカーソルの場合、ホット スポットは最初、左上隅 (座標 0,0) に置かれます。  
  
 既定では、イメージ エディターは、次の表に示すデバイス用の追加イメージの作成をサポートします。 幅、高さ、色の数のパラメーターを [[カスタム イメージの種類]](custom-image-dialog-box-image-editor-for-icons.md)ダイアログ ボックスに入力することにより、その他のデバイス用のイメージを作成することができます。  
  
> [!NOTE]
>  イメージ エディターを使用すると、32 ビット イメージを表示できます。ただし、編集はできません。  
  
|色|幅 (ピクセル単位)|高さ (ピクセル単位)|  
|-----------|----------------------|-----------------------|  
|白黒|16|16|  
|白黒|32|32|  
|白黒|48|48|  
|白黒|64|64|  
|白黒|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [新しいデバイス イメージの作成 (アイコンやカーソル)](../windows/creating-a-device-image-image-editor-for-icons.md)  
  
-   [別のディスプレイ デバイスのイメージの追加](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [デバイス イメージのコピー](../windows/copying-a-device-image-image-editor-for-icons.md)  
  
-   [デバイス イメージの削除](../windows/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [デバイス イメージの透明な領域または反転領域の作成](../windows/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [256 色のアイコンまたはカーソルの作成](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [カーソルのホット スポットの設定](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)   
 [アイコン](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [カーソル](http://msdn.microsoft.com/library/windows/desktop/ms646970)

