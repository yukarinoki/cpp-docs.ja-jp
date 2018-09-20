---
title: OpenMP ディレクティブ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 983a71920e9e7ce390ab8c64e81886db0d459450
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389449"
---
# <a name="openmp-directives"></a>OpenMP ディレクティブ

OpenMP API で使用するディレクティブへのリンクを提供します。

Visual C には、次の OpenMP ディレクティブがサポートされています。

|ディレクティブ|説明|
|---------------|-----------------|
|[atomic](../../../parallel/openmp/reference/atomic.md)|指定するアトミックに更新されるメモリの場所。|
|[barrier](../../../parallel/openmp/reference/barrier.md)|チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまでのすべてのスレッドがバリアで一時停止します。|
|[critical](../../../parallel/openmp/reference/critical.md)|コードが、一度に 1 つのスレッドでのみ実行されるかを指定します。|
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|すべてのスレッドがすべての共有オブジェクトのメモリの同じビューを持つことを指定します。|
|[for](../../../parallel/openmp/reference/for-openmp.md)|行われる動作、スレッド間で除算する、並行領域内の for ループします。|
|[master](../../../parallel/openmp/reference/master.md)|マスター スレッドのみが、プログラムのセクションを実行することを指定します。|
|[順序付け](../../../parallel/openmp/reference/ordered-openmp-directives.md)|シーケンシャル ループのようなループを実行する必要があります 並行処理には、そのコードを指定します。|
|[parallel](../../../parallel/openmp/reference/parallel.md)|複数のスレッドを並列で実行されるコードは、並列領域を定義します。|
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|すべてのスレッド間で分配するコード セクションを識別します。|
|[single](../../../parallel/openmp/reference/single.md)|コードのセクションは、シングル スレッドで実行する必要があります指定できます。|
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|変数は、スレッドに対してプライベートであることを指定します。|

## <a name="see-also"></a>関連項目

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[句](../../../parallel/openmp/reference/openmp-clauses.md)