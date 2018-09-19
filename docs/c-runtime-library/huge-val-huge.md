---
title: HUGE_VAL、_HUGE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9917d614261afaffe28ea92f913799c429a9611
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060721"
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>構文

```

#include <math.h>

```

## <a name="remarks"></a>コメント

`HUGE_VAL`表現可能な最大の double 値です。 エラーが発生した場合に、多くのランタイム数値演算関数でこの値が返されます。 一部の関数について -`HUGE_VAL` が返されます。 `HUGE_VAL` は `_HUGE` と定義されますが、ランタイム数値演算関数は `HUGE_VAL` を返します。 一貫性を保つのため、コードでも `HUGE_VAL` を使用する必要があります。

## <a name="see-also"></a>参照

[グローバル定数](../c-runtime-library/global-constants.md)