---
title: num_threads |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e39d7db36c121add3598387de52ecb878059b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405269"
---
# <a name="numthreads"></a>num_threads

スレッドのチームでは、スレッドの数を設定します。

## <a name="syntax"></a>構文

```
num_threads(num)
```

### <a name="parameters"></a>パラメーター

*num*<br/>
スレッドの数

## <a name="remarks"></a>Remarks

`num_threads`句と同じ機能には、 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)関数。

`num_threads` 次のディレクティブに適用されます。

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [sections](../../../parallel/openmp/reference/sections-openmp.md)

詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)します。

## <a name="example"></a>例

参照してください[並列](../../../parallel/openmp/reference/parallel.md)の使用例については`num_threads`句。

## <a name="see-also"></a>関連項目

[句](../../../parallel/openmp/reference/openmp-clauses.md)