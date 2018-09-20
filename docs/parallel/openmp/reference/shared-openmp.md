---
title: 共有 (OpenMP) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 118fa1eb75e8b943b6b490c158e5e21522d57e6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441331"
---
# <a name="shared-openmp"></a>shared (OpenMP)

すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。

## <a name="syntax"></a>構文

```
shared(var)
```

### <a name="parameters"></a>パラメーター

*var*<br/>
共有する 1 つまたは複数の変数。 1 つ以上の変数が指定されている場合は、変数名をコンマで区切ります。

## <a name="remarks"></a>Remarks

スレッド間での変数を共有する別の方法は、 [copyprivate](../../../parallel/openmp/reference/copyprivate.md)句。

`shared` 次のディレクティブに適用されます。

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [sections](../../../parallel/openmp/reference/sections-openmp.md)

詳細については、次を参照してください。[共有 2.7.2.4](../../../parallel/openmp/2-7-2-4-shared.md)します。

## <a name="example"></a>例

参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)の使用例については`shared`します。

## <a name="see-also"></a>関連項目

[句](../../../parallel/openmp/reference/openmp-clauses.md)