---
title: OpenMP データ型
ms.date: 10/23/2018
f1_keywords:
- OpenMP data types
- omp_lock_t
- omp_nest_lock_t
helpviewer_keywords:
- OpenMP data types
- omp_lock_t OpenMP data type
- omp_nest_lock_t OpenMP data type
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
ms.openlocfilehash: bacb48194015f8fd6c80a9868af06702deceab6f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533771"
---
# <a name="openmp-data-types"></a>OpenMP データ型

OpenMP API で使用されるデータ型へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次のデータ型が含まれています。

|データ型|説明|
|---------|-----------|
|[omp_lock_t](#omp-lock-t)|ロック、ロックが使用できるかどうか、またはスレッドがロックを所有しているかどうかの状態を保持する型。|
|[omp_nest_lock_t](#omp-nest-lock-t)|ロックに関する情報の次の情報の 1 つを保持する型: ロックが使用可能なかどうかと、ロックと入れ子のカウントを所有するスレッドの id。|

## <a name="omp-lock-t"></a>omp_lock_t

ロック、ロックが使用できるかどうか、またはスレッドがロックを所有しているかどうかの状態を保持する型。

次の機能使用`omp_lock_t`:

- [omp_init_lock](openmp-functions.md#omp-init-lock)
- [omp_destroy_lock](openmp-functions.md#omp-destroy-lock)
- [omp_set_lock](openmp-functions.md#omp-set-lock)
- [omp_unset_lock](openmp-functions.md#omp-unset-lock)
- [omp_test_lock](openmp-functions.md#omp-test-lock)

詳細については、次を参照してください。 [3.2 ロック関数](../../../parallel/openmp/3-2-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_lock 関数](openmp-functions.md#omp-init-lock)の使用例については`omp_lock_t`します。

## <a name="omp-nest-lock-t"></a>omp_nest_lock_t

次のようなロックについての情報を保持する型: ロックが使用可能なかどうかと、ロックと入れ子のカウントを所有するスレッドの id。

次の機能使用`omp_nest_lock_t`:

- [omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock)
- [omp_destroy_nest_lock](openmp-functions.md#omp-destroy-nest-lock)
- [omp_set_nest_lock](openmp-functions.md#omp-set-nest-lock)
- [omp_unset_nest_lock](openmp-functions.md#omp-unset-nest-lock)
- [omp_test_nest_lock](openmp-functions.md#omp-test-nest-lock)

詳細については、次を参照してください。 [3.2 ロック関数](../../../parallel/openmp/3-2-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock)の使用例については`omp_nest_lock_t`します。
