---
title: 3.1.6 omp_in_parallel 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22b491695d2ae49336d7d8998af64e724f344d87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686283"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 関数
**Omp_in_parallel**関数は、並列で実行される並列領域の動的な範囲内で呼び出された場合に 0 以外の値を返します。 それ以外の場合は 0 を返します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 この関数は、シリアル化される入れ子になった領域を含む、並列で実行される領域内から呼び出された場合は 0 以外の値を返します。