---
title: 2.6.6 ordered コンストラクト |Microsoft ドキュメント
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
ms.openlocfilehash: fa66d9fb8a0a9af2fc33497690bfe67a3ea5d717
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690346"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered コンストラクト
構造化ブロック次、**注文**ディレクティブが順次ループ内でのイテレーションが実行される順序で実行します。 構文、**注文**ディレクティブは、次のようにします。  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 **注文**ディレクティブはの動的な範囲内である必要があります、**の**または**の並列**を構築します。 **の**または**の並列**するディレクティブ、**注文**コンストラクト バインドする必要がありますが、**順序付け**句で説明するよう指定[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。 実行時に、**の**または**の並列**で構築、**注文**句、**注文**構造が厳密に実行される、ループの順次実行で実行される順序。  
  
 制限は、**注文**ディレクティブは、次のとおり。  
  
-   ループのイテレーション、**の**コンストラクト必要があります、同じ順序付けられたディレクティブは、2 回以上実行されず、1 つ以上実行する必要がありますいない**順序付け**ディレクティブです。