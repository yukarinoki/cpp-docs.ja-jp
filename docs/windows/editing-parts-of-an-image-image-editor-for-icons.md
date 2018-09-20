---
title: 一部のイメージ (アイコン用イメージ エディター) の編集 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9340180049d85b1b5385d49c7b358c3fd791ce9d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391476"
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>イメージの一部の編集 (アイコン用イメージ エディター)

標準の編集操作を行うことができます: 切り取り、コピー、消去、および移動-で、[選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)選択範囲がイメージ全体またはその一部だけであるかどうか、です。 **イメージ**エディターを使用して、 **Windows クリップボード**、間でのイメージを転送することができます、**イメージ**エディターおよびその他の Windows アプリケーション。

さらに、画像全体またはその一部だけが含まれて かどうか、選択範囲のサイズを変更できます。

### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>現在の選択範囲を切り取ってクリップボードに移動するには

1. をクリックして**切り取り**上、**編集**メニュー。

### <a name="to-copy-the-selection"></a>選択範囲をコピーするには

1. サイズ変更ハンドルを除く上または任意の場所の選択範囲の枠線内でポインターを置きます。

2. 押しながら、 **Ctrl**キーの選択範囲を新しい場所にドラッグするとします。 元の選択範囲の領域は変更されません。

3. 現在の場所にあるイメージには、選択範囲をコピーするには、選択カーソルの外側をクリックします。

### <a name="to-paste-the-clipboard-contents-into-an-image"></a>イメージにクリップボードの内容を貼り付ける

1. **編集**] メニューの [選択**貼り付け**します。

   選択範囲の境界線で囲まれた、クリップボードの内容は、ウィンドウの左上隅に表示されます。

2. 選択範囲の境界線内でポインターを配置し、イメージに目的の場所にイメージをドラッグします。

3. 新しい場所にあるイメージを固定するには、選択境界線の外側をクリックします。

### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>クリップボードに移動することがなく現在の選択範囲を削除するには

1. **編集**] メニューの [選択**削除**します。

   選択範囲の元の領域を現在の背景色で塗りつぶします。

   > [!NOTE]
   > アクセスすることができます、**切り取り**、**コピー**、**貼り付け**、および**削除**を右クリックしてコマンド、**リソース ビュー**ウィンドウ。

### <a name="to-move-the-selection"></a>選択範囲を移動するには

1. サイズ変更ハンドルを除く上または任意の場所の選択範囲の枠線内でポインターを置きます。

2. 新しい位置にドラッグします。

3. 新しい場所にある画像の選択範囲を固定するには、選択範囲の境界線の外側をクリックします。

選択した場合、描画の詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)