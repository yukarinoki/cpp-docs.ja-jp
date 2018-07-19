---
title: 3.3.1 omp_get_wtime 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71296d23df72464ed730713566c95e2403760a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689494"
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime 関数
`omp_get_wtime` 「過去の時間」からの秒数で関数が経過ウォール クロック時間に等しいにある倍精度浮動小数点値を返します。  実際「の時間、過去に」は任意、されるわけでは、アプリケーション プログラムの実行中に変更しないようにします。 形式は次のとおりです。  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 次の例で示すように、経過時間を測定する関数が使用されることが予想されます。  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 返される時間は、「スレッドごとの時間」を使用するアプリケーションに参加しているすべてのスレッドでグローバルに一貫している必要がないものでは、します。