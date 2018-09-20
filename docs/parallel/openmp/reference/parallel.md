---
title: 並列 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38b5bd4d277987be78cbd3714302c8b7f704b90f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405217"
---
# <a name="parallel"></a>parallel

複数のスレッドを並列で実行されるコードは、並列領域を定義します。

## <a name="syntax"></a>構文

```
#pragma omp parallel [clauses]
{
   code_block
}
```

## <a name="arguments"></a>引数

*句*<br/>
(省略可能)0 個以上の句。  サポートされている句の一覧については、「解説」を参照してください。**並列**します。

## <a name="remarks"></a>Remarks

**並列**ディレクティブは、次の OpenMP 句をサポートしています。

- [copyin](../../../parallel/openmp/reference/copyin.md)

- [default](../../../parallel/openmp/reference/default-openmp.md)

- [firstprivate](../../../parallel/openmp/reference/firstprivate.md)

- [if](../../../parallel/openmp/reference/if-openmp.md)

- [num_threads](../../../parallel/openmp/reference/num-threads.md)

- [private](../../../parallel/openmp/reference/private-openmp.md)

- [reduction](../../../parallel/openmp/reference/reduction.md)

- [shared](../../../parallel/openmp/reference/shared-openmp.md)

**並列**でもでき、[セクション](../../../parallel/openmp/reference/sections-openmp.md)と[の](../../../parallel/openmp/reference/for-openmp.md)ディレクティブ。

詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)します。

## <a name="example"></a>例

次の例では、スレッドの数を設定し、並列領域を定義する方法を示します。 既定では、スレッドの数は、マシン上の論理プロセッサの数と同じです。 たとえば、ハイパースレッディングが有効になっている 1 つの物理プロセッサを搭載したコンピューターがある場合は、2 つの論理プロセッサと 2 つのスレッドがあります。

```
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="comment"></a>コメント

出力の順序は、別々 のコンピューターで異なることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)