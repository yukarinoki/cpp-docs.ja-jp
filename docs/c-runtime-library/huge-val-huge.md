---
description: '詳細については、次を参照してください: HUGE_VAL、_HUGE'
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
api_name:
- _HUGE
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: c4109b61b9af65681ca2a006a3839e3d0338fa73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253144"
---
# <a name="huge_val-_huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>構文

```
#include <math.h>
```

## <a name="remarks"></a>解説

`HUGE_VAL`表現可能な最大の double 値です。 エラーが発生した場合に、多くのランタイム数値演算関数でこの値が返されます。 一部の関数について -`HUGE_VAL` が返されます。 `HUGE_VAL` は `_HUGE` と定義されますが、ランタイム数値演算関数は `HUGE_VAL` を返します。 一貫性を保つのため、コードでも `HUGE_VAL` を使用する必要があります。

## <a name="see-also"></a>関連項目

[グローバル定数](../c-runtime-library/global-constants.md)
