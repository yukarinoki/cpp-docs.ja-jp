---
title: 4.3 OMP_DYNAMIC |Microsoft Docs
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
ms.openlocfilehash: c15fa9d8c9d86b736bfc577a3b17e9809ec9baaf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439199"
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

**OMP_DYNAMIC**環境変数を有効または動的に調整が明示的に有効になっているか、を呼び出すことによって無効になっている場合を除き、並行領域の実行に使用できるスレッドの数を動的に調整を無効にします**omp_set_dynamic**ライブラリ ルーチン。 その値である必要があります**TRUE**または**FALSE**します。

場合設定**TRUE**、システム リソースを最大限に活用する、ランタイム環境での並列領域を実行するために使用されるスレッドの数を調整することがあります。  場合設定**FALSE**、動的に調整が無効になっています。 既定の条件では、実装定義されます。

例:

```
setenv OMP_DYNAMIC TRUE
```

## <a name="cross-references"></a>クロス リファレンス

- 並列領域の詳細については、次を参照してください。[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの。

- **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ。