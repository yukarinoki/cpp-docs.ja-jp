---
title: 2.6.6 ordered コンストラクト
ms.date: 11/04/2016
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
ms.openlocfilehash: fe6ad4adf2a4fcccfefe3c3585d9c88c0a118931
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615801"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered コンストラクト

構造化ブロックの後、**注文**ディレクティブはシーケンシャル ループのイテレーションが実行は順序で実行されます。 構文、**注文**ディレクティブを次に示します。

```
#pragma omp ordered new-linestructured-block
```

**注文**ディレクティブはの動的範囲内である必要があります、**の**または**の並列**を構築します。 **の**または**の並列**するディレクティブ、**注文**コンストラクトにバインドする必要がありますが、**注文**」の説明に従って指定された句[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。 実行に、**の**または**の並列**で構築、**注文**句、**注文**構造が厳密で実行される、ループの順次実行で実行する順序。

制限は、**注文**ディレクティブは、次のとおり。

- 使用して、ループのイテレーションを**の**コンストラクトする必要があります、同じ順序付けられたディレクティブは 2 回以上実行されず、1 つ以上実行する必要がありますいない**注文**ディレクティブ。