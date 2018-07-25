---
title: 編集 (アイコン用イメージ エディター) イメージの一部の |Microsoft ドキュメント
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
ms.openlocfilehash: b33a591a2f38062b5eaf81b0f56ab73a36f4c90c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876853"
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>イメージの一部の編集 (アイコン用イメージ エディター)
標準の編集操作を行うことができます: 切り取り、コピー、解除、および移動 — 上、[選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)選択範囲が画像全体またはその一部だけであるかどうか、します。 イメージ エディターは、Windows のクリップボードを使用しているために、イメージ エディターとその他の Windows アプリケーションの間でイメージを転送できます。  
  
 さらに、画像全体または一部だけが含まれているかどうか、選択範囲のサイズを変更できます。  
  
### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>現在の選択範囲を切り取って、クリップボードに移動するには  
  
1.  をクリックして**切り取り**上、**編集**メニュー。  
  
### <a name="to-copy-the-selection"></a>選択範囲をコピーするには  
  
1.  ポインターを選択範囲の境界線の内側または任意の場所にサイズ変更ハンドルを除くします。  
  
2.  押しながら、 **CTRL**キーの選択範囲を新しい場所にドラッグするとします。 元の選択範囲の領域は変更されません。  
  
3.  現在の場所にイメージには、選択範囲をコピーするには、選択範囲のカーソルの外部をクリックします。  
  
### <a name="to-paste-the-clipboard-contents-into-an-image"></a>イメージにクリップボードの内容を貼り付ける  
  
1.  **編集**] メニューの [選択**貼り付け**です。  
  
     選択範囲の境界線で囲まれた、クリップボードの内容は、ウィンドウの左上隅に表示されます。  
  
2.  選択範囲の境界線内でポインターを配置し、目的の場所に、画像上にイメージをドラッグします。  
  
3.  新しい場所にイメージを固定するには、選択範囲の境界線外をクリックします。  
  
### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>クリップボードに移動せずに現在の選択範囲を削除するには  
  
1.  **編集**] メニューの [選択**削除**です。  
  
     選択範囲の元の領域を現在の背景色で塗りつぶします。  
  
    > [!NOTE]
    >  切り取り、コピー、貼り付けにアクセスし、リソース ビュー ウィンドウで右クリックしてコマンドを削除できます。  
  
### <a name="to-move-the-selection"></a>選択範囲を移動するには  
  
1.  ポインターを選択範囲の境界線の内側または任意の場所にサイズ変更ハンドルを除くします。  
  
2.  新しい位置にドラッグします。  
  
3.  新しい場所に画像の選択範囲を固定するには、選択境界線の外側をクリックします。  
  
 選択範囲を使用した描画の詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

