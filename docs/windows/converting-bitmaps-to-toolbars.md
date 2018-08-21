---
title: ビットマップ ツールバーからへの変換 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor, converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74829769644c28cf13a6a6a2631f9bbef1e602a9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645520"
---
# <a name="converting-bitmaps-to-toolbars"></a>ビットマップからツール バーへの変換
新しいツールバーを作成するには、ビットマップを変換します。 グラフィック ビットマップからツールバーのボタンのイメージに変換します。 通常はビットマップでは、ボタンごとに 1 つのイメージの 1 つのビットマップ ボタン イメージがいくつか含まれています。 イメージのサイズにすることができます。既定では、イメージの高さ、幅 16 ピクセルです。 ボタンのイメージのサイズを指定することができます、[新規ツール バー リソース ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)を選択すると**ツール バー エディター**から、**イメージ**イメージ エディターでのメニュー。  
  
### <a name="to-convert-bitmaps-to-a-toolbar"></a>ビットマップからツールバーに変換するには  
  
1.  既存のビットマップ リソースを開き、[イメージ エディター](../windows/image-editor-for-icons.md)します。 (ビットマップがまだ .rc ファイルにされていない場合は、.rc ファイルを右クリックし、選択**インポート**、ショートカット メニューから、.rc ファイルに追加するビットマップに移動します をクリックし、**オープン**)。  
  
2.  **イメージ**] メニューの [選択**ツール バー エディター**します。  
  
     [新規ツール バー リソース ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)が表示されます。 幅と高さのビットマップに合わせてアイコン イメージを変更することができます。 ツールバー エディターで、ツール バー イメージが表示されます。  
  
3.  変換を完了するには、コマンドを変更**ID**のボタンを使用して、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しい入力**ID**か、選択、 **ID**ドロップダウン リストから。  
  
    > [!TIP]
    >  **プロパティ**ウィンドウにはタイトル バーの画鋲ボタンが含まれています。 このボタンをクリックすると、有効または無効に**自動的に隠す**ウィンドウ。 有効にする個々 のプロパティ ウィンドウを再び開くことがなく、すべてのツール バー ボタン プロパティをすばやく切り替える、**自動的に隠す**オフため、**プロパティ**ウィンドウが静止したままになります。  
  
 使用して、新しいツールバーのボタンのコマンド Id を変更することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しいツールバーの編集方法の詳細については、次を参照してください。[作成、移動、およびツール バー ボタンの編集](../windows/creating-moving-and-editing-toolbar-buttons.md)します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツールバーの新規作成](../windows/creating-new-toolbars.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)