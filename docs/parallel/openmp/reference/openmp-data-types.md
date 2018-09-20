---
title: OpenMP データ型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b41eaf7012c1d119071281f98177e4a4d841890b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410073"
---
# <a name="openmp-data-types"></a>OpenMP のデータ型

OpenMP API で使用されるデータ型へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次のデータ型が含まれています。

|データ型|説明|
|---------------|-----------------|
|[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)|ロック、ロックが使用できるかどうか、またはスレッドがロックを所有しているかどうかの状態を保持する型。|
|[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)|ロックに関する情報の次の情報の 1 つを保持する型: ロックが使用可能なかどうかと、ロックと入れ子のカウントを所有するスレッドの id。|

## <a name="see-also"></a>関連項目

[ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)