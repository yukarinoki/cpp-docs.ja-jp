---
title: 'アイコンとカーソル: ディスプレイ デバイス (C++ アイコン用イメージ エディター) のイメージ リソース'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.icon
helpviewer_keywords:
- cursors [C++], creating
- image resources [C++], display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices [C++], creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
ms.openlocfilehash: 5d5e252dd7841d923a6de42f06518838f4314563
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586655"
---
# <a name="icons-and-cursors-image-resources-for-display-devices-c-image-editor-for-icons"></a>アイコンとカーソル: ディスプレイ デバイス (C++ アイコン用イメージ エディター) のイメージ リソース

アイコンとカーソルは、グラフィカルなリソースで、表示デバイスの種類ごとに異なるサイズや色スキームの複数のイメージを含めることができます。 さらに、カーソルには「ホット スポット」があります。これは、その位置を追跡するために Windows で使用されるロケーションです。 アイコンとカーソルの両方が作成され、編集を使用して、**イメージ**エディターで、ビットマップ、およびその他のイメージ。

新しいアイコンまたはカーソルを作成するときに、**イメージ**エディターが最初に、標準タイプのイメージを作成します。 イメージは最初、画面の色 (透明) で塗られます。 イメージがカーソルの場合、ホット スポットは最初、左上隅 (座標 0,0) に置かれます。

既定で、**イメージ**エディターは、次の表に示すようにデバイスの追加イメージの作成をサポートしています。 幅、高さ、色の数のパラメーターを [[カスタム イメージの種類]](custom-image-dialog-box-image-editor-for-icons.md)ダイアログ ボックスに入力することにより、その他のデバイス用のイメージを作成することができます。

> [!NOTE]
> 使用して、**イメージ エディター**、32 ビットのイメージを表示することができますが、編集することはできません。

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

- [新しいデバイス イメージの作成 (アイコンやカーソル)](../windows/creating-a-device-image-image-editor-for-icons.md)

- [別のディスプレイ デバイスのイメージの追加](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)

- [デバイス イメージのコピー](../windows/copying-a-device-image-image-editor-for-icons.md)

- [デバイス イメージの削除](../windows/deleting-a-device-image-image-editor-for-icons.md)

- [デバイス イメージの透明な領域または反転領域の作成](../windows/creating-transparent-or-inverse-regions-in-device-images.md)

- [256 色のアイコンまたはカーソルの作成](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)

- [カーソルのホット スポットの設定](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)<br/>
[アイコン](https://msdn.microsoft.com/library/windows/desktop/ms646973)<br/>
[カーソル](https://msdn.microsoft.com/library/windows/desktop/ms646970)