---
title: バリア |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- barrier
dev_langs:
- C++
helpviewer_keywords:
- barrier OpenMP directive
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c220106d62bf65505c9c5b48085a9ee3e67fe0cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415032"
---
# <a name="barrier"></a>barrier

チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまでのすべてのスレッドがバリアで一時停止します。

## <a name="syntax"></a>構文

```
#pragma omp barrier
```

## <a name="remarks"></a>Remarks

`barrier`ディレクティブに OpenMP 句がサポートされていません。

詳細については、次を参照してください。 [2.6.3 barrier ディレクティブ](../../../parallel/openmp/2-6-3-barrier-directive.md)します。

## <a name="example"></a>例

使用する方法の例については`barrier`を参照してください[マスター](../../../parallel/openmp/reference/master.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)