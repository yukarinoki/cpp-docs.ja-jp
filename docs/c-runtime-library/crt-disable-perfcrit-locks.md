---
description: '詳細については、次を参照してください: _CRT_DISABLE_PERFCRIT_LOCKS'
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b96e29fad635ac9e7f3d622ace3c43bb26c8805a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195685"
---
# <a name="_crt_disable_perfcrit_locks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

I/O 操作でパフォーマンスが重要なロックを無効にします。

## <a name="syntax"></a>構文

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>解説

このシンボルを定義すると、すべての I/O 操作でシングル スレッドの I/O モデルを前提とすることで、シングル スレッドの I/O バウンド プログラムのパフォーマンスを改善できます。 詳細については、「[マルチスレッド ライブラリのパフォーマンス](../c-runtime-library/multithreaded-libraries-performance.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[グローバル定数](../c-runtime-library/global-constants.md)
