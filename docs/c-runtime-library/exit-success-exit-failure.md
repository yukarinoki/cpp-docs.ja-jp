---
description: '詳細については、次を参照してください: EXIT_SUCCESS、EXIT_FAILURE'
title: EXIT_SUCCESS、EXIT_FAILURE
ms.date: 06/25/2018
f1_keywords:
- EXIT_FAILURE
- EXIT_SUCCESS
helpviewer_keywords:
- EXIT_SUCCESS constant
- EXIT_FAILURE constant
ms.assetid: ff2c82cb-c0bb-4556-a812-59aa278bfac5
ms.openlocfilehash: d92481635d553de4cfaa9bd026fd577cd51f6eff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300061"
---
# <a name="exit_success-exit_failure"></a>EXIT_SUCCESS、EXIT_FAILURE

## <a name="required-header"></a>必須ヘッダー

```c
#include <stdlib.h>
```

## <a name="remarks"></a>解説

これらは [exit](reference/exit-exit-exit.md) 関数と [_exit](reference/exit-exit-exit.md) 関数の引数であり、[atexit](reference/atexit.md) 関数と [_onexit](reference/onexit-onexit-m.md) 関数の戻り値です。

|定数|定義済みの値|
|-|-|
|EXIT_SUCCESS|0|
|EXIT_FAILURE|1|

## <a name="see-also"></a>関連項目

[グローバル定数](../c-runtime-library/global-constants.md)
