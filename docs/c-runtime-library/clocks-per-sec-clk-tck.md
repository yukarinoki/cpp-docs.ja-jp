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
ms.openlocfilehash: c3c7eac1db91abf7a84e424f7166402f346d3e4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033577"
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