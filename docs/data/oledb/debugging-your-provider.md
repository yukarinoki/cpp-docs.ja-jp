---
title: プロバイダーのデバッグ |Microsoft Docs
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
ms.openlocfilehash: fc4461bb29bb9b9c706177c4dcd2134d37d697e0
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989906"
---
# <a name="debugging-your-provider"></a>プロバイダーのデバッグ

プロバイダーをデバッグする 2 つの方法はあります。  
  
- プロセスでは、プロバイダーが作成される、ために、通常、OLE DB コンシューマー テンプレートと、プロバイダーにステップ インを使用して一部のコンシューマー コードを作成できます。  
  
- Visual C に付属する ITEST ユーティリティを使用することができます。  
  
## <a name="to-use-the-itest-utility"></a>ITEST ユーティリティを使用するには  
  
1. プロバイダーのプロジェクトを開きます。  
  
1. **プロジェクト** メニューのをクリックして**設定**します。  
  
1. **プロパティ ページ**ダイアログ ボックスで、をクリックして、**デバッグ**タブ。  
  
1. **デバッグ セッションの実行可能ファイル**ボックスで、ITEST アプリケーションを選択します。  
  
1. ブレークポイントを設定し、通常どおりにデバッグします。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)