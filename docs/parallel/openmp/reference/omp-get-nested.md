---
title: omp_get_nested |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20a7378ba7e7f6dcec55cfe265dd0873bdc1fd38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46371954"
---
# <a name="ompgetnested"></a>omp_get_nested

入れ子になった並列処理が有効かどうかを示す値を返します。

## <a name="syntax"></a>構文

```
int omp_get_nested( );
```

## <a name="return-value"></a>戻り値

0 以外の場合は、入れ子になった並列化が有効にします。

## <a name="remarks"></a>Remarks

入れ子になった並列処理を指定した[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)と[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)します。

詳細については、次を参照してください。 [3.1.10 omp_get_nested 関数](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)します。

## <a name="example"></a>例

参照してください[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)の使用例については`omp_get_nested`します。

## <a name="see-also"></a>関連項目

[関数](../../../parallel/openmp/reference/openmp-functions.md)