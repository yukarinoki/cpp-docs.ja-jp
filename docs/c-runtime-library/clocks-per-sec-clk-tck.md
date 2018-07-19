---
title: CLOCKS_PER_SEC、CLK_TCK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
dev_langs:
- C++
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbcc64419a34ff763f3e116474687fbadf055f42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387402"
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC、CLK_TCK
## <a name="syntax"></a>構文  
  
```  
  
#include <time.h>  
```  
  
## <a name="remarks"></a>コメント  
 `clock` 関数の戻り値であり、`CLOCKS_PER_SEC` で除算された秒単位の時間を表します。 `CLK_TCK` も同じものですが、古い形式とされます。  
  
## <a name="see-also"></a>参照  
 [clock](../c-runtime-library/reference/clock.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)