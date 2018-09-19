---
title: 推論による依存ファイルと規則 |Microsoft Docs
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
ms.openlocfilehash: c13ae7784ff40b39642ce26fd062a1aab80f2d4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707552"
---
# <a name="inferred-dependents-and-rules"></a>推論による依存ファイルと推論規則

NMAKE では、該当する推論規則が存在する場合のターゲットの推論による依存ファイルを想定しています。 場合、ルールが適用されます。

- *toext*ターゲットの拡張子に一致します。

- *fromext*一致のターゲットの基本名とを持つファイルの拡張子が現在または指定したディレクトリに存在します。

- *fromext*に[します。サフィックス](../build/dot-directives.md); の他の*fromext*照合ルールではより高度な**します。サフィックス**優先順位。

- 高度な明示的な依存ファイルを持たない**します。サフィックス**優先順位。

推論による依存ファイルには、予期しない副作用が生じる可能性があります。 ターゲットの説明のブロックにコマンドが含まれている場合 (nmake の) は、ルールで、コマンドではなく、これらのコマンドを実行します。

## <a name="see-also"></a>関連項目

[推論規則](../build/inference-rules.md)