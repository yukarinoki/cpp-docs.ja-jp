---
title: 3.1.10 omp_get_nested 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f447da6957cb385ace918120eb7ed7a5420e9f0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686722"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested 関数
`omp_get_nested`関数 0 を返します入れ子になった並列処理が有効になっている場合は 0 以外の値が無効な場合です。 入れ子になった並列処理の詳細については、40 ページの 3.1.9 セクションを参照してください。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 実装が入れ子になった並列処理を実装していない場合、この関数は常に 0 を返します。