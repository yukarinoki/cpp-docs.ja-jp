---
title: ダイアログ ボックスのサイズと場所を指定する |Microsoft ドキュメント
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
ms.openlocfilehash: cc4c6867f5ed3791414619257fec33db4c632553
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890578"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>ダイアログ ボックスの位置とサイズの指定
場所と、ダイアログ ボックスだけでなく、場所のサイズと、内のコントロールのサイズは、ダイアログ単位で測定されます。 個々 のコントロールと、ダイアログ ボックスの値は、Visual Studio のステータス バーの選択した場合の右下に表示されます。  
  
 設定できる 3 つのプロパティがある、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window) ダイアログ ボックスを画面に表示される表示を指定します。 Center プロパティがブール値です。値を True に設定した場合、ダイアログ ボックスは常に、画面の中央に表示されます。 False に設定すると、ダイアログ ボックスが表示画面に表示される場所を明示的に定義するプロパティに対して画面と 1/3 プロパティを設定できます。 位置プロパティは、{X = 0、Y = 0} として定義されている表示領域の左上隅からのオフセットの値です。 位置がまたに基づいて、**絶対配置**プロパティ: True の場合、座標画面に対して相対的です。 False の場合、座標は、ダイアログの所有者のウィンドウに対して相対的です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

