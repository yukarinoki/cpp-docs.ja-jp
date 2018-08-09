---
title: ダイアログ ボックスのサイズと場所を指定する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a3a9a629ec138659a7b0d2aba2460aced31fc74
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649004"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>ダイアログ ボックスの位置とサイズの指定
場所とダイアログ ボックスでは、だけでなく、場所のサイズと、内のコントロールのサイズは、ダイアログ単位で測定されます。 個々 のコントロールと、ダイアログ ボックスの値は、Visual Studio のステータス バーの選択した場合の右下に表示されます。  
  
 設定できる 3 つのプロパティがある、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window) ダイアログ ボックスを画面に表示を指定します。 Center プロパティがブール値です。値を True に設定した場合 ダイアログ ボックスは常に、画面の中央に表示されます。 False に設定した場合は、XPos と YPos プロパティ ダイアログ ボックスが表示され、画面上の場所を明示的に定義し、設定できます。 位置プロパティは、{X = 0、Y = 0} として定義されている表示領域の左上隅からのオフセットの値です。 位置もに基づいて、 **Absolute Align**プロパティ: 座標が画面を基準には、True の場合は、ダイアログ ボックスのオーナー ウィンドウに対する相対座標は、False の場合、します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)