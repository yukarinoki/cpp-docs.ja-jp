---
title: 2.7.2.3 lastprivate |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08f331862d6e48b1c0882382285ddffa9699e79c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate
`lastprivate`句によって提供される機能のスーパー セットを提供する、`private`句。 構文、`lastprivate`句を次に示します。  
  
```  
lastprivate(variable-list)  
```  
  
 指定された変数、*変数一覧*が`private`句のセマンティクスです。 ときに、`lastprivate`句が、work-sharing コンス トラクター、それぞれの値を示すディレクティブで使用されます`lastprivate`に関連付けられているループ、または、構文的に最後のセクション ディレクティブの順番に前回のイテレーションから変数を割り当て、変数の元のオブジェクト。 前回のイテレーションではない変数が値を割り当てる、**の**または**の並列**、または、構文上の最後のセクションで、**のセクションでは**または**parallel sections の**ディレクティブ、不確定な値が、構築後にあります。 割り当てられていないサブオブジェクトは、作成後も不確定な値を持ちます。  
  
 制限、`lastprivate`句は、次のようにします。  
  
-   すべての制限`private`を適用します。  
  
-   として指定されているクラス型の変数`lastprivate`あいまいでないアクセス可能なコピー代入演算子を持つ必要があります。  
  
-   変数は、並行領域内でプライベートをまたはに表示される、`reduction`の句、**並列**ディレクティブを指定することはできません、 `lastprivate` parallel コンストラクトにバインドされる動作共有ディレクティブの句。