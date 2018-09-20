---
title: firstprivate |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d070b8de3cf0382447c3b8e756140892dcd85edc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387121"
---
# <a name="firstprivate"></a>firstprivate

Parallel コンストラクトの前に存在するため、各スレッドは、変数の独自のインスタンスである必要があり、変数の値で、変数を初期化する必要がありますを指定します。

## <a name="syntax"></a>構文

```
firstprivate(var)
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`var`|Parallel コンストラクトの前に存在するので、変数の値は、各スレッド内のインスタンスを持つ変数は初期化されます。 1 つ以上の変数が指定されている場合は、変数名をコンマで区切ります。|

## <a name="remarks"></a>Remarks

## <a name="remarks"></a>Remarks

`firstprivate` 次のディレクティブに適用されます。

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [sections](../../../parallel/openmp/reference/sections-openmp.md)

- [single](../../../parallel/openmp/reference/single.md)

詳細については、次を参照してください。 [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md)します。

## <a name="example"></a>例

使用する例については`firstprivate`、例を参照してください。[プライベート](../../../parallel/openmp/reference/private-openmp.md)します。

## <a name="see-also"></a>関連項目

[句](../../../parallel/openmp/reference/openmp-clauses.md)