---
title: omp_destroy_lock 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_destroy_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_destroy_lock OpenMP function
ms.assetid: b73ab036-b76f-4e42-82ff-c89db2edf7c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22ee3b0f262742223c57149d7e828a58910223fe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400134"
---
# <a name="ompdestroylock"></a>omp_destroy_lock

ロックは初期化されません。

## <a name="syntax"></a>構文

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)で初期化された[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)します。

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)します。

## <a name="example"></a>例

参照してください[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)の使用例については`omp_destroy_lock`します。

## <a name="see-also"></a>関連項目

[関数](../../../parallel/openmp/reference/openmp-functions.md)