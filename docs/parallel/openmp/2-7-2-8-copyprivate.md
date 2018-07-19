---
title: 2.7.2.8 copyprivate |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c809f297da5059a98915e8055dfe23f45074366f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691604"
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate
**Copyprivate**句がプライベート変数を使用して、他のメンバーにチームの 1 つのメンバーから値をブロードキャストするメカニズムを提供します。 このような共有変数を提供することは困難 (たとえば、レベルごとに異なる変数を必要とする再帰) がある場合に、値の共有変数を使用する代わりにすることをお勧めします。 **Copyprivate**句でのみ使用できます、**単一**ディレクティブです。  
  
 構文、 **copyprivate**句を次に示します。  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 効果、 **copyprivate**に関連付けられている構造化ブロックの実行後に発生の句の変数リストに変数を**単一**構築、および任意のスレッドの前に、チームは、コンス トラクターの末尾にバリアが残されています。 その後、それぞれの変数に、チームの他のすべてのスレッドで、*変数一覧*、その変数の対応する値を持つ (割り当て) した場合と同じ定義されるコンストラクトを実行したスレッド内の変数の構造化ブロックです。  
  
 制限は、 **copyprivate**句は、次のようにします。  
  
-   指定されている変数、 **copyprivate**句は必要がありますには表示されない、**プライベート**または**firstprivate**同じ句**単一**ディレクティブです。  
  
-   場合、**単一**でディレクティブ、 **copyprivate**並列領域の動的範囲で、句を検出したで指定されたすべての変数、 **copyprivate**句がある必要がありますそれを囲むコンテキスト内でプライベートです。  
  
-   指定されている変数、 **copyprivate**句は、アクセスできる明確なコピー代入演算子を持つ必要があります。