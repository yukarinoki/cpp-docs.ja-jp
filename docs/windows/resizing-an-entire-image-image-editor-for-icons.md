---
title: 全体のイメージ (アイコン用イメージ エディター) のサイズ変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- size [C++], images
- images [C++], resizing
- resizing images
ms.assetid: 10782937-7eb4-4340-bdec-618ee7d7904b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5465ccacf6fb051e787cf390c82108cb9344d203
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613110"
---
# <a name="resizing-an-entire-image-image-editor-for-icons"></a>イメージ全体のサイズ変更 (アイコン用イメージ エディター)

### <a name="to-resize-an-entire-image-using-the-properties-window"></a>[プロパティ] ウィンドウを使用してイメージ全体のサイズを変更するには

1. イメージを変更するプロパティを開きます。

2. **幅**と**高さ**ボックス、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、目的のサイズを入力します。

   イメージのサイズを増加した場合、**イメージ**エディターは、イメージ、下、右またはその両方を拡張し、新しいリージョンを現在の背景色で塗りつぶします。 イメージが伸縮されていません。

   場合は、イメージのサイズを小さくと、**イメージ**エディター右端または下端またはその両方でイメージをトリミングします。

   > [!NOTE]
   > 使用することができます、**幅**と**高さ**部分的な選択範囲のサイズを変更しないように、のみ全体イメージのサイズを変更するプロパティ。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[イメージのサイズ変更](../windows/resizing-an-image-image-editor-for-icons.md)