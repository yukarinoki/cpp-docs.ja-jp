---
title: setvbuf 定数
ms.date: 11/04/2016
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
ms.openlocfilehash: 25c25741f54c1383a5bad9038b5b5d761dacdd89
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458050"
---
# <a name="setvbuf-constants"></a>setvbuf 定数

## <a name="syntax"></a>構文

```

#include <stdio.h>

```

## <a name="remarks"></a>コメント

これらの定数は、`setvbuf` のバッファーの種類を表します。

使用可能な値は、次のマニフェスト定数によって与えられます。

|定数|説明|
|--------------|-------------|
|`_IOFBF`|フル バッファリング: `setvbuf` の呼び出しで指定したバッファーが使用され、そのサイズは `setvbuf` の呼び出しで指定したとおりになります。 バッファー ポインターが **NULL** の場合は、指定したサイズで自動的に割り当てられたバッファーが使用されます。|
|`_IOLBF`|`_IOFBF` と同じ。|
|`_IONBF`|`setvbuf` 呼び出しの引数に関係なく、バッファーは使用されません。|

## <a name="see-also"></a>参照

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)