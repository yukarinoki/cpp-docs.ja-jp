---
title: 2.7.2.8 copyprivate
ms.date: 11/04/2016
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
ms.openlocfilehash: d4df1b4216014d3cd15be1480d2f83334fddb72d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622912"
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

**Copyprivate**句がプライベート変数を使用して、他のメンバーにチームの 1 つのメンバーから値をブロードキャストするメカニズムを提供します。 このような共有変数を提供するが難しい (たとえばの各レベルで別の変数を必要とする再帰) ときに、値の共有変数を使用する代わりにすることをお勧めします。 **Copyprivate**句にのみ表示できる、**単一**ディレクティブ。

構文、 **copyprivate**句を次に示します。

```

copyprivate(
variable-list
)

```

効果、 **copyprivate**に関連付けられている構造化ブロックの実行後に発生する句の変数リストに、変数に、**単一**構築、内のスレッドの前に、チームは、コンス トラクターの末尾にバリアを脱退しました。 その後、それぞれの変数に、チームの他のすべてのスレッドで、*変数一覧*、対応する値をその変数になります (割り当て) した場合と同じ定義されている、コンストラクトを実行するスレッドの変数の構造化ブロックです。

制限は、 **copyprivate**句は、次のとおり。

- 指定されている変数、 **copyprivate**句は必要がありますには表示されない、**プライベート**または**firstprivate**同じ句**単一**ディレクティブ。

- 場合、**単一**ディレクティブ、 **copyprivate**で指定されたすべての変数を並行領域の動的範囲で、句が発生しました、 **copyprivate**句がある必要があります外側のコンテキストではプライベートです。

- 指定されている変数、 **copyprivate**句は、アクセス可能な明確なコピー代入演算子を指定する必要があります。