---
title: ATL レジストラーのスクリプトを作成する |Microsoft Docs
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
ms.openlocfilehash: abffe3c8d0a107c48c3a14a9bf584122229ad3b7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767261"
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts

レジストラー スクリプトでは、システム レジストリへの API に基づくのではなく、データ ドリブンのアクセスを提供します。 レジストリにキーを追加するスクリプトで 1 つまたは 2 つの行がかかるので、データに基づくアクセスは通常は効率的です。

[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)COM サーバーのレジストラー スクリプトを自動的に生成されます。 このスクリプトは、オブジェクトに関連付けられた .rgs ファイルで見つかります。

ATL レジストラーのスクリプト エンジンでは、実行時に、レジストラー スクリプトを処理します。 ATL は、サーバーのセットアップ中にスクリプト エンジンを自動的に呼び出します。

この記事では、次のレジストラー スクリプトに関連するトピックについて説明します。

- [バッカス ナウア記法 (BNF) 構文を理解する](../atl/understanding-backus-nauer-form-bnf-syntax.md)

- [パース ツリーを理解する](../atl/understanding-parse-trees.md)

- [レジストリ スクリプトの例](../atl/registry-scripting-examples.md)

- [置き換え可能パラメーターの使用 (レジストラー プリプロセッサ)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [スクリプトの呼び出し](../atl/invoking-scripts.md)

## <a name="see-also"></a>関連項目

[レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)

