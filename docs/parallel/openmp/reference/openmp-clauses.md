---
title: OpenMP 句 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd0a8f66f9b0d027671629998597955b3aa69e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378335"
---
# <a name="openmp-clauses"></a>OpenMP 句

OpenMP API で使用される句へのリンクを提供します。

Visual C には、次の OpenMP 句がサポートされています。

|句|説明|
|------------|-----------------|
|[copyin](../../../parallel/openmp/reference/copyin.md)|スレッドのマスター スレッドの値にアクセスできるように、 [threadprivate](../../../parallel/openmp/reference/threadprivate.md)変数。|
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。|
|[default](../../../parallel/openmp/reference/default-openmp.md)|並列領域では、対象範囲外の変数の動作を指定します。|
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Parallel コンストラクトの前に存在するため、各スレッドは、変数の独自のインスタンスである必要があり、変数の値で、変数を初期化する必要がありますを指定します。|
|[if](../../../parallel/openmp/reference/if-openmp.md)|直列または並列でループを実行する必要があるかどうかを指定します。|
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|変数の外側のコンテキストのバージョンを最後の反復処理 (for ループ コンストラクト) または最後のセクション (#pragma セクション) を実行したスレッドのプライベート バージョンと同じに設定されているを指定します。|
|[nowait](../../../parallel/openmp/reference/nowait.md)|ディレクティブ内の暗黙のバリアをオーバーライドします。|
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|スレッドのチームでは、スレッドの数を設定します。|
|[順序付け](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|並列で必要な[の](../../../parallel/openmp/reference/for-openmp.md)ステートメント場合、[注文](../../../parallel/openmp/reference/ordered-openmp-directives.md)ディレクティブが、ループ内で使用されます。|
|[private](../../../parallel/openmp/reference/private-openmp.md)|各スレッドは、変数の独自のインスタンスである必要がありますを指定します。|
|[reduction](../../../parallel/openmp/reference/reduction.md)|各スレッドに対してプライベートである 1 つまたは複数の変数を並行領域の最後のリダクション演算の件名を指定します。|
|[schedule](../../../parallel/openmp/reference/schedule.md)|適用されます、[の](../../../parallel/openmp/reference/for-openmp.md)ディレクティブ。|
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。|

## <a name="see-also"></a>関連項目

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)