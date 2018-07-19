---
title: プロバイダーのデバッグ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c6258ddd3fd4317c608cb20486c364918fb5c73a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106395"
---
# <a name="debugging-your-provider"></a>プロバイダーのデバッグ
ストアには、プロバイダーをデバッグする 2 つの方法があります。  
  
-   プロセスでは、プロバイダーが作成された、ためには、通常、OLE DB コンシューマー テンプレートとプロバイダーをステップを使用して一部のコンシューマー コードを作成できます。  
  
-   Visual C に付属している ITEST ユーティリティを使用することができます。  
  
### <a name="to-use-the-itest-utility"></a>ITEST ユーティリティを使用するには  
  
1.  プロバイダー プロジェクトを開きます。  
  
2.  **プロジェクト** メニューのをクリックして**設定**です。  
  
3.  **プロパティ ページ**ダイアログ ボックスで、をクリックして、**デバッグ**タブです。  
  
4.  **デバッグ セッションの実行可能ファイル**ボックスで、ITEST アプリケーションを選択します。  
  
5.  ブレークポイントを設定し、通常どおりにデバッグします。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)