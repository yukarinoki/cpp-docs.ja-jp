---
title: アイコン用イメージ エディター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, images
- resource editors, graphics
- Image editor [C++]
- resource editors, Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63ab877506c0b38563868374312c8f63bc28333e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583533"
---
# <a name="image-editor-for-icons"></a>アイコン用イメージ エディター

イメージ エディターには、イメージの作成と編集に使用できる広範なツール セットと、ツール バーのビットマップの作成に役立つ機能が用意されています。 **[イメージ]** メニューのコマンドや、 **[イメージ エディター]** ツール バーのツールを使用して、ビットマップ、アイコン、カーソルだけでなく、GIF 形式や JPEG 形式のイメージも編集できます。

イメージ エディターでは、次の作業ができます。

- [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)

- [色の調整](../windows/working-with-color-image-editor-for-icons.md)

- [アイコンとカーソル : ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [イメージ エディターのアクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)

**イメージ エディター**ウィンドウには、2 つのペイン分割バーで、イメージの 2 つのビューが表示されます。 分割バーを左右にドラッグすると、ペインの相対サイズを変更できます。 アクティブなペインには、選択境界線が表示されます。

**イメージ エディター**ウィンドウは、ニーズと好みに合わせて調整できます。 [拡大率を変更](../windows/changing-the-magnification-factor-image-editor-for-icons.md) したり、 [ピクセル グリッドの表示と非表示を切り替え](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)たりできます。

> [!NOTE]
> 使用して、**イメージ エディター**、32 ビットのイメージを表示することができますが、編集することはできません。

## <a name="visual-studio-image-library"></a>Visual Studio Image Library

無料でダウンロードすることができます、 **Visual Studio Image Library**多くのアニメーション、ビットマップ、およびアプリケーションで使用できるアイコンが含まれています。 ライブラリをダウンロードする方法の詳細については、「 [Visual Studio Image Library](/visualstudio/designers/the-visual-studio-image-library)」を参照してください。

## <a name="managed-resources"></a>マネージド リソース

使用することができます、**イメージ**エディターと[バイナリ エディター](binary-editor.md)マネージ プロジェクトのリソース ファイルを使用します。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)  
[アイコン](http://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)