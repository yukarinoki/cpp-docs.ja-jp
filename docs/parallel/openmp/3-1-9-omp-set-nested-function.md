---
title: 3.1.9 omp_set_nested 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df08d6eb1a93ff5852c239757d5f917e9777919b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687284"
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested 関数
**Omp_set_nested**関数を有効または入れ子になった並列処理を無効にします。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 場合*入れ子になった*入れ子になった 0 に評価される、既定値は、並列処理が無効にし、入れ子になった並列領域のシリアル化され、現在のスレッドによって実行します。 場合*入れ子になった*評価 0 以外の値には、入れ子になった並列処理が有効であり、入れ子になった並列領域は入れ子になったチームを形成する追加のスレッドを配置可能性があります。  
  
 この関数は、プログラムの部分から呼び出されたときに、上記の効果を場所、 **omp_in_parallel**関数は 0 を返します。 プログラムの部分から呼び出されたかどうかはここで、 **omp_in_parallel**関数には、0 以外の値が返されます、この関数の動作は未定義です。  
  
 この呼び出しに優先、 **OMP_NESTED**環境変数。  
  
 入れ子になった並列処理を有効にすると、入れ子になった並列領域の実行に使用するスレッドの数は、実装定義します。 その結果、OpenMP 準拠の実装は、入れ子になった並列処理が有効な場合でも、入れ子になった並列領域をシリアル化が許可されます。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **OMP_NESTED**環境変数を参照してください[セクション 4.4](../../parallel/openmp/4-4-omp-nested.md) 49 ページにします。  
  
-   **omp_in_parallel**関数を参照してください[セクション 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md)ページ 38 です。