---
description: 詳細については、「レジストラースクリプトの作成」を参照してください。
title: ATL レジストラーのスクリプトの作成
ms.date: 05/14/2014
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
ms.openlocfilehash: a3ce4855460e65eda5ab522bc16f39191da02a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153188"
---
# <a name="creating-registrar-scripts"></a>レジストラー スクリプトの作成

レジストラー スクリプトにより、API ではなく、データに基づいてシステム レジストリにアクセスできます。 データに基づくアクセスは、レジストリにキーを追加するために、スクリプトに 1、2 行しか必要としないため、一般に効率的になります。

[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)によって、COM サーバーのレジストラー スクリプトが自動的に生成されます。 このスクリプトは、オブジェクトに関連付けられた .rgs ファイルで見つかります。

ATL レジストラーのスクリプト エンジンによって、実行時にレジストラー スクリプトが処理されます。 ATL によって、サーバーのセットアップ時にスクリプト エンジンが自動的に呼び出されます。

この記事では、レジストラー スクリプトに関する次のトピックについて説明します。

- [Backus-Naur form (BNF) 構文を理解する](../atl/understanding-backus-naur-form-bnf-syntax.md)

- [解析ツリーについて](../atl/understanding-parse-trees.md)

- [レジストリスクリプトの例](../atl/registry-scripting-examples.md)

- [置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [スクリプトの呼び出し](../atl/invoking-scripts.md)

## <a name="see-also"></a>関連項目

[レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)
