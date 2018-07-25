---
title: ビットマップ ツールバーからへの変換 |Microsoft ドキュメント
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
ms.openlocfilehash: e80bee7ef9bfe52abf63ac959475c5d8dbcf0ece
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872628"
---
# <a name="converting-bitmaps-to-toolbars"></a>ビットマップからツール バーへの変換
新しいツールバーを作成するには、ビットマップを変換します。 グラフィック ビットマップからツールバーのボタンのイメージに変換します。 通常、ビットマップには、1 つのビットマップのボタンごとに 1 つのイメージのいくつかのボタン イメージが含まれています。 イメージのサイズにすることができます。既定では 16 ピクセルとイメージの高さです。 ボタンのイメージのサイズを指定することができます、[新規ツールバー ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)からツール バー エディターを選択すると、**イメージ**イメージ エディターでのメニュー。  
  
### <a name="to-convert-bitmaps-to-a-toolbar"></a>ツールバーのビットマップを変換するには  
  
1.  既存のビットマップ リソースを開く、[イメージ エディター](../windows/image-editor-for-icons.md)です。 (ビットマップが .rc ファイルにない場合、.rc ファイルを右クリックし、選択**インポート**、ショートカット メニューを .rc ファイルに追加するビットマップに移動し、クリックして**開く**)。  
  
2.  **イメージ**] メニューの [選択**ツール バー エディター**です。  
  
     [新規ツールバー ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)が表示されます。 ビットマップに合わせてアイコン イメージの高さと幅を変更することができます。 ツール バー エディター ツール バー イメージが表示されます。  
  
3.  変換を完了するには、コマンドを変更**ID**  ボタンを使用して、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しい入力**ID**かを選択して、 **ID**ドロップダウン リストからです。  
  
    > [!TIP]
    >  [プロパティ] ウィンドウには、タイトル バーのプッシュピン ボタンが含まれています。 このボタンをクリックすると有効またはウィンドウの自動非表示を無効にします。 すばやくを順番にすべてのツール バー ボタン プロパティを windows の個々 のプロパティを再度開くことがなく、オフにする自動非表示にするため、[プロパティ] ウィンドウがまだ定常化します。  
  
 使用して、新しいツールバーのボタンのコマンド Id を変更することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しいツールバーの編集方法の詳細については、次を参照してください。[作成、移動、および編集ツール バー ボタン](../windows/creating-moving-and-editing-toolbar-buttons.md)です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツールバーの新規作成](../windows/creating-new-toolbars.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)

