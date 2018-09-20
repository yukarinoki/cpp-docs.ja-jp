---
title: omp_get_dynamic |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2b5a285ef019cd1752b60065f7040d9a937ce38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389890"
---
# <a name="ompgetdynamic"></a>omp_get_dynamic

以降の並列領域で使用できるスレッドの数を実行時に調整できるかどうかを示す値を返します。

## <a name="syntax"></a>構文

```
int omp_get_dynamic();
```

## <a name="return-value"></a>戻り値

0 以外の場合は、スレッドの動的な調整が有効です。

## <a name="remarks"></a>Remarks

スレッドの動的な調整を指定した[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)と[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)します。

詳細については、次を参照してください。 [3.1.7 omp_set_dynamic 関数](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)します。

## <a name="example"></a>例

参照してください[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)の使用例については`omp_get_dynamic`します。

## <a name="see-also"></a>関連項目

[関数](../../../parallel/openmp/reference/openmp-functions.md)