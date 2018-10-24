---
title: OpenMP データ型 |Microsoft Docs
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP data types
- omp_lock_t
- omp_nest_lock_t
dev_langs:
- C++
helpviewer_keywords:
- OpenMP data types
- omp_lock_t OpenMP data type
- omp_nest_lock_t OpenMP data type
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254dffebc258867088f738b10a11bf48d31bd0a4
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990070"
---
# <a name="openmp-data-types"></a>OpenMP のデータ型

OpenMP API で使用されるデータ型へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次のデータ型が含まれています。

データ型                           | 説明
----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[omp_lock_t](#omp-lock-t)           | ロック、ロックが使用できるかどうか、またはスレッドがロックを所有しているかどうかの状態を保持する型。
[omp_nest_lock_t](#omp-nest-lock-t) | ロックに関する情報の次の情報の 1 つを保持する型: ロックが使用可能なかどうかと、ロックと入れ子のカウントを所有するスレッドの id。

## <a name="omp-lock-t"></a>omp_lock_t

ロック、ロックが使用できるかどうか、またはスレッドがロックを所有しているかどうかの状態を保持する型。

次の機能使用`omp_lock_t`:

- [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)
- [omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)
- [omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)
- [omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)
- [omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)

詳細については、次を参照してください。 [3.2 ロック関数](../../../parallel/openmp/3-2-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)の使用例については`omp_lock_t`します。

## <a name="omp-nest-lock-t"></a>omp_nest_lock_t

次のようなロックについての情報を保持する型: ロックが使用可能なかどうかと、ロックと入れ子のカウントを所有するスレッドの id。

次の機能使用`omp_nest_lock_t`:

- [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)
- [omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)
- [omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)
- [omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)
- [omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)

詳細については、次を参照してください。 [3.2 ロック関数](../../../parallel/openmp/3-2-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)の使用例については`omp_nest_lock_t`します。
