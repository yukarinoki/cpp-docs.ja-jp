---
title: setvbuf 定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a367522c2f22007abcf24cdf74ada467d94b104
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032823"
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