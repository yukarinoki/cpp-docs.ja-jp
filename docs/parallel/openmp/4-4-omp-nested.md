---
title: 4.4 OMP_NESTED |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1779b75774a2177a0d6a4f0661406e28b479a7ee
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED`環境変数を有効または入れ子になった並列処理が有効になっている、または呼び出すことによって無効になっている場合を除き、入れ子になった並列処理を無効になります、 `o` **mp_set_nested**ライブラリ ルーチンです。 場合に設定**TRUE**、入れ子になった並列処理が有効である場合に設定されている**FALSE**、入れ子になった並列処理が無効になっています。 既定値は**FALSE**です。  
  
 例:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>クロス リファレンス  
  
-   `omp_set_nested` 関数を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページのです。