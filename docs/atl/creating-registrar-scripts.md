---
title: ATL レジストラーのスクリプトを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e140e66ee24d8333d25c0c2942924c7a9db4965b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354434"
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts
レジストラー スクリプトは、システム レジストリへの API に基づくのではなく、データ ドリブンのアクセスを提供します。 データ ドリブンのアクセスは、レジストリ キーを追加するスクリプト内で 1 つまたは 2 つの行がかかるのでに通常より効率的です。  
  
 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)COM サーバー用のレジストラー スクリプトを自動的に生成されます。 このスクリプトは、オブジェクトに関連付けられている .rgs ファイルで参照できます。  
  
 ATL レジストラーのスクリプト エンジンでは、実行時に、レジストラー スクリプトを処理します。 ATL は、サーバーのセットアップ中に、スクリプト エンジンを自動的に呼び出します。  
  
 この記事では、レジストラー スクリプトに関連する次のトピックについて説明します。  
  
-   [バッカス ナウア記法 (BNF) 構文を理解する](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [パース ツリーを理解する](../atl/understanding-parse-trees.md)  
  
-   [レジストリ スクリプトの例](../atl/registry-scripting-examples.md)  
  
-   [置き換え可能パラメーターの使用 (レジストラー プリプロセッサ)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [スクリプトの呼び出し](../atl/invoking-scripts.md)  
  
## <a name="see-also"></a>関連項目  
 [レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)

