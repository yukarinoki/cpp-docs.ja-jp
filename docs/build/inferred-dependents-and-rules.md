---
title: 推論による依存ファイルとルール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aae09fd756e0eb4eab3031beb5b4cba8c4d35a40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368045"
---
# <a name="inferred-dependents-and-rules"></a>推論による依存ファイルと推論規則
NMAKE では、適切な推論規則が存在する場合、ターゲット用の推論による依存ファイルが前提とします。 場合、ルールが適用されます。  
  
-   *toext*ターゲットの拡張子と一致します。  
  
-   *fromext*現在または指定されたディレクトリに存在する、ファイルの拡張子を持つターゲットの基本名と一致します。  
  
-   *fromext*に[です。サフィックス](../build/dot-directives.md)以外の他の*fromext*照合ルールでは、高い**です。サフィックス**優先度。  
  
-   明示的な依存が高くない**です。サフィックス**優先度。  
  
 推論による依存ファイルには、予期しない副作用が生じる可能性があります。 ターゲットの記述ブロックのコマンドが含まれている場合 (nmake の) は、ルールで、コマンドではなく、それらのコマンドを実行します。  
  
## <a name="see-also"></a>関連項目  
 [推論規則](../build/inference-rules.md)