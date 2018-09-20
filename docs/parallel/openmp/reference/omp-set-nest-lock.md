---
title: omp_set_nest_lock |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7ca097219297038728adc3924980e8c91e25ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438588"
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock

ロックが利用可能になるまで、スレッドの実行をブロックします。

## <a name="syntax"></a>構文

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)で初期化された[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)します。

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)します。

## <a name="examples"></a>使用例

参照してください[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)の使用例については`omp_set_nest_lock`します。

## <a name="see-also"></a>関連項目

[関数](../../../parallel/openmp/reference/openmp-functions.md)