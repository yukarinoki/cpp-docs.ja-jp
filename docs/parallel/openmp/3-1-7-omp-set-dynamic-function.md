---
title: 3.1.7 omp_set_dynamic 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 807e5739c571f7aa8e9f723a0a48c8c46f1e6d09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441565"
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic 関数

**Omp_set_dynamic**関数が有効にまたは並行領域の実行に使用できるスレッドの数を動的に調整を無効にします。 形式は次のとおりです。

```
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

場合*dynamic_threads*評価 0 以外の値を以降の並列領域を実行するために使用されるスレッドの数が自動的に環境によって調整されます、実行時システム リソースを最大限に活用します。 その結果、ユーザーによって指定されたスレッドの数は、最大スレッド数。 並列領域を実行する、チーム内のスレッドの数は固定です並列領域の間およびによって報告された、 **omp_get_num_threads**関数。

場合*dynamic_threads*評価を 0 に動的に調整が無効になっています。

この関数は、プログラムの部分から呼び出されたときに上記で説明した効果を**omp_in_parallel**関数は 0 を返します。 プログラムの部分から呼び出されたかどうか、 **omp_in_parallel**関数は 0 以外の値を返します、この関数の動作は未定義です。

呼び出し**omp_set_dynamic**経由での優先順位を持つ、 **OMP_DYNAMIC**環境変数。

動的に調整するスレッドの既定値は、実装定義です。 結果として、適切な実行のスレッドの特定の数に依存しているユーザー コードは、明示的に動的スレッドを無効にする必要があります。 実装には、スレッドの数を動的に調整する機能を提供する必要はありませんが、すべてのプラットフォームでの移植性をサポートするために、インターフェイスを提供する必要があります。

## <a name="cross-references"></a>クロス リファレンス

- **omp_get_num_threads**関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 ページ。

- **OMP_DYNAMIC**環境変数を参照してください[セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) [49] ページ。

- **omp_in_parallel**関数を参照してください[セクション 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 ページ。