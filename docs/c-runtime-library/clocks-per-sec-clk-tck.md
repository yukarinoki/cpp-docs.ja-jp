---
title: CLOCKS_PER_SEC、CLK_TCK
ms.date: 11/04/2016
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
ms.openlocfilehash: 40401028ef16f0d46baec92a37b2ba422d1e56ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621352"
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC、CLK_TCK

## <a name="syntax"></a>構文

```

#include <time.h>
```

## <a name="remarks"></a>コメント

`clock` 関数の戻り値であり、`CLOCKS_PER_SEC` で除算された秒単位の時間を表します。 `CLK_TCK` も同じものですが、古い形式とされます。

## <a name="see-also"></a>参照

[clock](../c-runtime-library/reference/clock.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)