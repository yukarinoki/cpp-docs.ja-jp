---
title: copyin |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 424bb8eaa41e3bbb0cf697df108adcef116e1b04
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379581"
---
# <a name="copyin"></a>copyin

スレッドのマスター スレッドの値にアクセスできるように、 [threadprivate](../../../parallel/openmp/reference/threadprivate.md)変数。

## <a name="syntax"></a>構文

```
copyin(var)
```

## <a name="parameters"></a>パラメーター

*var*<br/>
`threadprivate` Parallel コンストラクトの前に存在する場合に、マスターのスレッド内の変数の値で初期化する変数。

## <a name="remarks"></a>Remarks

`copyin` 次のディレクティブに適用されます。

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [sections](../../../parallel/openmp/reference/sections-openmp.md)

詳細については、次を参照してください。 [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md)します。

## <a name="example"></a>例

参照してください[threadprivate](../../../parallel/openmp/reference/threadprivate.md)の使用例については`copyin`します。

## <a name="see-also"></a>関連項目

[句](../../../parallel/openmp/reference/openmp-clauses.md)