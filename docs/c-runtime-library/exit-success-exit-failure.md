---
title: EXIT_SUCCESS、EXIT_FAILURE
ms.date: 06/25/2018
f1_keywords:
- EXIT_FAILURE
- EXIT_SUCCESS
helpviewer_keywords:
- EXIT_SUCCESS constant
- EXIT_FAILURE constant
ms.assetid: ff2c82cb-c0bb-4556-a812-59aa278bfac5
ms.openlocfilehash: 562c97b62840285719344d124d8df9944bec25cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519172"
---
# <a name="exitsuccess-exitfailure"></a>EXIT_SUCCESS、EXIT_FAILURE

## <a name="required-header"></a>必須ヘッダー

```c
#include <stdlib.h>
```

## <a name="remarks"></a>コメント

これらは [exit](reference/exit-exit-exit.md) 関数と [_exit](reference/exit-exit-exit.md) 関数の引数であり、[atexit](reference/atexit.md) 関数と [_onexit](reference/onexit-onexit-m.md) 関数の戻り値です。

|定数|定義済みの値|
|-|-|
|EXIT_SUCCESS|0|
|EXIT_FAILURE|1|

## <a name="see-also"></a>関連項目

[グローバル定数](../c-runtime-library/global-constants.md)
