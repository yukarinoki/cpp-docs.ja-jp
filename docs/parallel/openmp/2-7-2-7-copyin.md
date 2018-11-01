---
title: 2.7.2.7 copyin
ms.date: 11/04/2016
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
ms.openlocfilehash: 65bb8faba085e5582e779fa0e9d5bf1a91a39f0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545445"
---
# <a name="2727-copyin"></a>2.7.2.7 copyin

**Copyin**句に同じ値を代入するためのメカニズムを提供する**threadprivate**並列領域を実行する、チーム内の各スレッドの変数。 指定された各変数に対して、 **copyin**並列領域の先頭に、スレッド プライベート コピーへの代入した場合と同じ句では、チームのマスター スレッド内の変数の値をコピーします。 構文、 **copyin**句を次に示します。

```

copyin(
variable-list
)

```

制限、 **copyin**句は、次のとおり。

- 指定されている変数、 **copyin**句があいまいでないアクセス可能なコピー代入演算子を指定する必要があります。

- 指定されている変数、 **copyin**句がある必要があります、 **threadprivate**変数。