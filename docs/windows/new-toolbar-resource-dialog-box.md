---
title: 新しいツールバー ダイアログ ボックス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.newtoolbarresource
dev_langs:
- C++
helpviewer_keywords:
- New Toolbar Resource dialog box
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33c63357f0816fbf0d89058d4151ea5785f6f35a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015021"
---
# <a name="new-toolbar-resource-dialog-box"></a>[新規ツール バー リソース] ダイアログ ボックス
**新規ツール バー リソース** ダイアログ ボックスでは、ツール バー リソースを追加するボタンの高さと幅を指定できます。 既定では 16 × 15 ピクセルです。  
  
 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 設定した場合は、**ボタンの幅**512 には、4 つのボタンのみができます。 513 幅を設定する場合は、3 つのボタンのみができます。  
  
### <a name="button-width"></a>ボタンの幅  
 ビットマップ リソースからツール バー リソースに変換するツール バー ボタンの幅を入力する場所を提供します。 幅と高さを指定すると、画像がトリミングされ、標準ツールバーの色 (16 色) を使用する色が調整されます。  
  
### <a name="button-height"></a>ボタンの高さ  
 ビットマップ リソースからツール バー リソースに変換するツール バー ボタンの高さを入力する場所を提供します。 幅と高さを指定すると、画像がトリミングされ、標準ツールバーの色 (16 色) を使用する色が調整されます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツール バー ボタンのプロパティ](../windows/toolbar-button-properties.md)   
 [ビットマップ ツールバーからへの変換](../windows/converting-bitmaps-to-toolbars.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)