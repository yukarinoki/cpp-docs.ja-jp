---
title: OMP_DYNAMIC |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a2a4d660057ab83da39add7fd32bcff3e6d90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392139"
---
# <a name="ompdynamic"></a>OMP_DYNAMIC

OpenMP の実行時に、並行領域内のスレッドの数を調整できるかどうかを指定します。

## <a name="syntax"></a>構文

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

## <a name="remarks"></a>Remarks

`OMP_DYNAMIC`で環境変数をオーバーライドできます、 [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)関数。

OpenMP の標準の Visual C の実装の既定値は`OMP_DYNAMIC=FALSE`します。

詳細については、次を参照してください。 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)します。

## <a name="example"></a>例

次のコマンド セット、`OMP_DYNAMIC`環境変数を TRUE にします。

```
set OMP_DYNAMIC=TRUE
```

次のコマンドの現在の設定の表示、`OMP_DYNAMIC`環境変数。

```
set OMP_DYNAMIC
```

## <a name="see-also"></a>関連項目

[環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)