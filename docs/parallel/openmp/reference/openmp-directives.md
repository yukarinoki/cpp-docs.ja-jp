---
title: OpenMP ディレクティブ |Microsoft ドキュメント
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
ms.openlocfilehash: d7421f397b39c6d26c2e60042b25f37277afa5fd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-directives"></a>OpenMP ディレクティブ
OpenMP API で使用するディレクティブへのリンクを提供します。  
  
 Visual C には、次の OpenMP ディレクティブがサポートされています。  
  
|ディレクティブ|説明|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|指定するアトミックに更新されるメモリの場所。|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまで、すべてのスレッドがバリアで一時停止します。|  
|[critical](../../../parallel/openmp/reference/critical.md)|コードが、一度に 1 つのスレッドでのみ実行されるかを指定します。|  
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|すべてのスレッドがすべての共有オブジェクトのメモリについて同じビューを持つことを指定します。|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|行われる動作、スレッド間で除算、並行領域内の for ループします。|  
|[master](../../../parallel/openmp/reference/master.md)|マスター スレッドのみが、プログラムのセクションを実行することを指定します。|  
|[順序付け](../../../parallel/openmp/reference/ordered-openmp-directives.md)|順次ループと同様に実行されるループの並行処理の下には、そのコードを指定します。|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|同時に複数のスレッドで実行されるコードである並列領域を定義します。|  
|[sections](../../../parallel/openmp/reference/sections-openmp.md)|すべてのスレッド間で分配するコード セクションを識別します。|  
|[single](../../../parallel/openmp/reference/single.md)|コードのセクションをシングル スレッドで実行するように指定することができます。|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|変数が、スレッドに対してプライベートであることを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [句](../../../parallel/openmp/reference/openmp-clauses.md)