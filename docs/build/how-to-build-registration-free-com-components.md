---
title: '方法: 登録を必要としない COM コンポーネントをビルド |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e54327344d61cc70e68b528c5f88f3d30f5d185a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-build-registration-free-com-components"></a>方法 : 登録を必要としない COM をビルドする
登録を必要としない COM コンポーネントは、Dll に組み込まれているマニフェストのある COM コンポーネントです。  
  
### <a name="to-build-manifests-into-com-components"></a>COM コンポーネントにマニフェストをビルドするには  
  
1.  COM コンポーネントのプロジェクトのプロパティ ページを開きます。  
  
2.  展開、**構成プロパティ** ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**の入力し、出力**プロパティ ページ、および設定、**埋め込みマニフェスト**プロパティを等しく**はい**です。  
  
4.  **[OK]** をクリックします。  
  
5.  ソリューションをビルドします。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーション](http://msdn.microsoft.com/library/aa375190)   
 [サイド バイ サイド アセンブリの概要](http://msdn.microsoft.com/library/ff951640)   
 [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)