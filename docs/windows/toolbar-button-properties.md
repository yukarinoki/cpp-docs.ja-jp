---
title: ツール バー ボタンのプロパティ |Microsoft Docs
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
ms.openlocfilehash: a37e15c4235886eef1dbee958ec5c3da29caab0e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650119"
---
# <a name="toolbar-button-properties"></a>ツール バー ボタンのプロパティ
ツール バー ボタンのプロパティは次のとおりです。  
  
|プロパティ|説明|  
|--------------|-----------------|  
|**ID**|ボタンの ID を定義します。 ドロップダウンの一覧は、一般的な**ID**名。|  
|**Width**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|  
|**Height**|ボタンの高さを設定します。 1 つのボタンの高さがすべてのツールバーのボタンの高さを変更することに注意してください。 15 ピクセルをお勧めします。|  
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 \N と名を追加すると、そのツール バー ボタンにツールヒントが追加されます。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)します。|  
  
 **幅**と**高さ**のすべてのボタンに適用されます。 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 したがって、ボタンの幅を 512 に設定した場合は 4 つのボタンのみができ、513 幅を設定する場合は 3 つのボタンのみができます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツール バー ボタンのプロパティを変更します。](../windows/changing-the-properties-of-a-toolbar-button.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)