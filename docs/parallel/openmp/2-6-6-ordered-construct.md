---
title: 2.6.6 ordered コンストラクト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b83c3dfc13b231a1314343a1dff496acf7a99b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412198"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered コンストラクト

構造化ブロックの後、**注文**ディレクティブはシーケンシャル ループのイテレーションが実行は順序で実行されます。 構文、**注文**ディレクティブを次に示します。

```
#pragma omp ordered new-linestructured-block
```

**注文**ディレクティブはの動的範囲内である必要があります、**の**または**の並列**を構築します。 **の**または**の並列**するディレクティブ、**注文**コンストラクトにバインドする必要がありますが、**注文**」の説明に従って指定された句[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。 実行に、**の**または**の並列**で構築、**注文**句、**注文**構造が厳密で実行される、ループの順次実行で実行する順序。

制限は、**注文**ディレクティブは、次のとおり。

- 使用して、ループのイテレーションを**の**コンストラクトする必要があります、同じ順序付けられたディレクティブは 2 回以上実行されず、1 つ以上実行する必要がありますいない**注文**ディレクティブ。