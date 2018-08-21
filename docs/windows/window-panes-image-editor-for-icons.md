---
title: ウィンドウ ペイン (アイコン用イメージ エディター) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a38341f6c6bcbcdec6bb4e6f5e5820fa759e6dab
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652026"
---
# <a name="window-panes-image-editor-for-icons"></a>ウィンドウ ペイン (アイコン用イメージ エディター)
**イメージ エディター**ウィンドウは通常の分割バーで区切られた 2 つのペインでイメージを表示します。 1 つのビューは、実際のサイズと、他方は拡大 (既定の倍率は 6)。 これら 2 つのペインでビューが自動的に更新されます。 1 つのペインで行った変更は、他のすぐに表示します。 2 つのペインを簡単に、イメージを個々 のピクセルの区別を、同時に確認できます、作業のイメージの実際のサイズのビューへの影響の拡大表示で作業します。  
  
 左側のウィンドウの使用が必要な限り多くの領域 (の半分、**イメージ**ウィンドウ)、イメージの 1:1 のビュー (既定値) を表示します。 右側のウィンドウには、拡大した画像 (既定では 6:1 拡大率) が表示されます。 できます[倍率を変更](../windows/changing-the-magnification-factor-image-editor-for-icons.md)各ペインを使用して、**拡大**ツールを[イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)またはアクセラレータ キーを使用します。  
  
 小さいウィンドウを大きくことができます、**イメージ エディター**ウィンドウと、2 つのペインを使用して、大きなイメージのさまざまなリージョンを表示します。 これを選択するウィンドウをクリックします。  
  
 分割バーにポインターを合わせて、分割バーを右または左に移動して、ペインの相対的なサイズを変更できます。 分割バーは、1 つのペインで作業する場合、いずれかの側に移動できます。  
  
 場合、**イメージ エディター**できますでは、ウィンドウが 4 の倍数で拡大以上[ピクセル グリッドを表示](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)イメージ内の個々 のピクセルを区切る。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)