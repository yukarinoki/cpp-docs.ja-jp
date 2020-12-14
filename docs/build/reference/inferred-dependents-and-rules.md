---
description: '詳細情報: 推論される依存関係とルール'
title: 推論による依存ファイルと推論規則
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 9f4c1d14d18c9c693a7bd71f9207ff36aede8e22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191278"
---
# <a name="inferred-dependents-and-rules"></a>推論による依存ファイルと推論規則

適用可能な推論規則が存在する場合、NMAKE はターゲットに対して推論された依存を想定します。 次の場合にルールが適用されます。

- *toext* は、ターゲットの拡張機能と一致します。

- *fromext* は、ターゲットのベース名を持ち、現在のディレクトリまたは指定されたディレクトリに存在するファイルの拡張子と一致します。

- *fromext* は in [です。サフィックス](dot-directives.md)。照合ルール内の他の *fromext* には、より高いがありません **。サフィックス** の優先度。

- 明示的に依存するものはありません **。サフィックス** の優先度。

推論による依存関係により、予期しない副作用が発生する可能性があります。 ターゲットの description ブロックにコマンドが含まれている場合、NMAKE は、規則内のコマンドではなく、これらのコマンドを実行します。

## <a name="see-also"></a>関連項目

[推論規則](inference-rules.md)
