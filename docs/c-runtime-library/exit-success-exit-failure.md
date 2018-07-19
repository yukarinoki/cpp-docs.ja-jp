---
title: EXIT_SUCCESS、EXIT_FAILURE | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- EXIT_FAILURE
- EXIT_SUCCESS
dev_langs:
- C++
helpviewer_keywords:
- EXIT_SUCCESS constant
- EXIT_FAILURE constant
ms.assetid: ff2c82cb-c0bb-4556-a812-59aa278bfac5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671946045de5cfd2a7a34e163b459ebfc3bb5479
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954349"
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
