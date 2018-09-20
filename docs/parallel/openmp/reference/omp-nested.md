---
title: OMP_NESTED |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c90878ce96cf1639c983be899ba13eccf1f040e8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376541"
---
# <a name="ompnested"></a>OMP_NESTED

入れ子になった並列処理が有効になってこと、入れ子になった並列処理を有効になっているかを無効になっている場合を除き、かどうかを指定します。`omp_set_nested`します。

## <a name="syntax"></a>構文

```
set OMP_NESTED[=TRUE | =FALSE]
```

## <a name="remarks"></a>Remarks

`OMP_NESTED`で環境変数をオーバーライドできます、 [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)関数。

OpenMP の標準の Visual C の実装の既定値は`OMP_DYNAMIC=FALSE`します。

詳細については、次を参照してください。 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)します。

## <a name="example"></a>例

次のコマンド セット、`OMP_NESTED`環境変数を TRUE にします。

```
set OMP_NESTED=TRUE
```

次のコマンドの現在の設定の表示、`OMP_NESTED`環境変数。

```
set OMP_NESTED
```

## <a name="see-also"></a>関連項目

[環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)