---
title: ATL サービス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule
dev_langs:
- C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db13b443e605168389f0a9bc767ba29a75d4234d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354793"
---
# <a name="atl-services"></a>ATL サービス
サービスで実行されるように、ATL COM オブジェクトを作成するには、ATL プロジェクト ウィザードでのサーバー オプションの一覧からサービス (EXE) を選択します。 ウィザードはから派生するクラスを作成し、`CAtlServiceModuleT`してサービスを実装します。  
  
 ATL COM オブジェクトをサービスとしてビルドするとき、のみ、ローカル サーバーとして登録され、コントロール パネルの サービスの一覧には表示されません。 これは、サービスとしてよりもローカル サーバーとサービスをデバッグしやすくなっているためです。 サービスとしてインストールするには、コマンド プロンプトで、次を実行します。  
  
 `YourEXE` `.exe /Service`  
  
 これをアンインストールするには次の手順を実行します。  
  
 `YourEXE` `.exe /UnregServer`  
  
 このセクションの最初の 4 つのトピックの実行中に発生するアクションを説明する`CAtlServiceModuleT`メンバー関数。 これらのトピックは、関数が呼び出されて通常と同じ順序で表示されます。 これらのトピックの理解を深めるためには参照として ATL プロジェクト ウィザードで生成されたソース コードを使用することをお勧めします。 これらの最初の 4 つのトピックは次のとおりです。  
  

-   [CAtlServiceModuleT::Start 関数](../atl/reference/catlservicemodulet-class.md#start)  
  
-   [CAtlServiceModuleT::ServiceMain 関数](../atl/reference/catlservicemodulet-class.md#servicemain)  
  
-   [主要な関数](../atl/reference/catlservicemodulet-class.md#run)  
  
-   [CAtlServiceModuleT::Handler 関数](../atl/reference/catlservicemodulet-class.md#handler)  
  
 最後の 3 つのトピックでは、サービスの開発に関連する概念について説明します。  
  
-   [レジストリ エントリ](../atl/registry-entries.md)ATL サービス  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [デバッグのヒント](../atl/debugging-tips.md)ATL サービス  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)

