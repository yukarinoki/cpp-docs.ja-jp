---
title: _FREEENTRY、_USEDENTRY
ms.date: 11/04/2016
f1_keywords:
- USEDENTRY
- _USEDENTRY
- _FREEENTRY
- FREEENTRY
helpviewer_keywords:
- _USEDENTRY constant
- _FREEENTRY constant
- FREEENTRY constant
- USEDENTRY constant
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
ms.openlocfilehash: 3bf05807930373a905a5bf71cf4ebc1f119056a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513985"
---
# <a name="freeentry-usedentry"></a>_FREEENTRY、_USEDENTRY

## <a name="syntax"></a>構文

```
#include <malloc.h>
```

## <a name="remarks"></a>コメント

これらの定数は、`_heapwalk` ルーチンから **_HEAPINFO** 構造体の **_useflag** 要素に割り当てられた値を表します。 これらはヒープ エントリの状態を示します。

## <a name="see-also"></a>参照

[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)