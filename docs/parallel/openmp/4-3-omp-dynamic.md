---
title: 4.3 OMP_DYNAMIC |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f376fe639d9bca58b6e2bd55fd081b88921a7342
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
**OMP_DYNAMIC**環境変数を有効または動的に調整が明示的に有効になっているか、を呼び出すことによって無効にしない限り、並列領域を実行するために使用できるスレッドの数が動的に調整を無効になります**omp_set_dynamic**ライブラリ ルーチンです。 その値がある必要があります**TRUE**または**FALSE**です。  
  
 場合に設定**TRUE**、並列領域の実行に使用されるスレッドの数は、システム リソースを最大限に活用する、ランタイム環境で調整される可能性があります。  場合設定**FALSE**、動的に調整が無効になっています。 既定の条件では、実装定義されます。  
  
 例:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   並列領域の詳細については、次を参照してください。[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。