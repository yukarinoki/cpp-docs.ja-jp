---
title: 推論規則 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2baa4bdd749e7553d052600cc9efe524ec09910d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="inference-rules"></a>推論規則
推論規則は、ターゲットを更新し、ターゲットの依存ファイルを推測するコマンドを指定します。 推論規則の拡張機能が 1 つのターゲットと一致し、同じ基本名がある依存します。 推論のルールは、ユーザー定義または定義済みです。定義済みの規則を再定義することができます。  
  
 期限切れの依存関係には、コマンドがあるない場合、場合[です。サフィックス](../build/dot-directives.md)依存ファイルの拡張子と一致するターゲットおよび既存のルールは、現在または指定したディレクトリにファイル (nmake の) の使用が含まれています。 複数の規則には、既存のファイルが一致する場合、**です。サフィックス** ボックスの一覧を決定を使用する以外のリストの優先順位は左から右にします。 依存ファイルが存在せず、別の記述ブロック内のターゲットに表示されていない場合は、推論規則を作成できます欠落している依存同じ基本名の別のファイルから。 記述ブロックのターゲットには、依存ファイルやコマンドがなければ、推論規則は、ターゲットを更新できます。 推論規則は、記述ブロックが存在しない場合でも、コマンド ラインのターゲットをビルドできます。 (Nmake の) は、明示的な依存ファイルが指定されている場合でも、推論による依存ファイルの規則を呼び出すことがあります。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [ルールの定義](../build/defining-a-rule.md)  
  
 [バッチモード規則](../build/batch-mode-rules.md)  
  
 [定義済み規則](../build/predefined-rules.md)  
  
 [推論による依存ファイルと規則](../build/inferred-dependents-and-rules.md)  
  
 [推論規則の優先順位](../build/precedence-in-inference-rules.md)  
  
## <a name="see-also"></a>関連項目  
 [NMAKE リファレンス](../build/nmake-reference.md)