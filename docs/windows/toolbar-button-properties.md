---
title: ツール バー ボタン プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons (in Toolbar editor), setting properties
- Toolbar editor, toolbar button properties
- status bars, active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e61ba7e8720c755ce26408826c56a5c1fc9d51e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="toolbar-button-properties"></a>ツール バー ボタンのプロパティ
ツール バー ボタンのプロパティは次のとおりです。  
  
|プロパティ|説明|  
|--------------|-----------------|  
|**ID**|ボタンの ID を定義します。 ボックスの一覧は、一般的な**ID**名。|  
|**Width**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|  
|**Height**|ボタンの高さを設定します。 1 つのボタンの高さがツールバーのすべてのボタンの高さを変更することに注意してください。 15 ピクセルをお勧めします。|  
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 \N と名を追加すると、そのツール バー ボタンにツールヒントが追加されます。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)です。|  
  
 **幅**と**高さ**のすべてのボタンに適用します。 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 これを 512 ボタンの幅を設定する場合は、4 つのボタンをのみ持つことができ、513 幅を設定する場合は、3 つのボタンをのみ持つことができます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツール バー ボタンのプロパティの変更](../windows/changing-the-properties-of-a-toolbar-button.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)

