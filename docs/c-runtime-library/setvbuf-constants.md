---
description: '詳細について: setvbuf 定数'
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
ms.openlocfilehash: 375c692f4437bd60c84e37c857e078d9386ffb1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277012"
---
# <a name="setvbuf-constants"></a>setvbuf 定数

## <a name="syntax"></a>構文

```
#include <stdio.h>
```

## <a name="remarks"></a>解説

これらの定数は、`setvbuf` のバッファーの種類を表します。

使用可能な値は、次のマニフェスト定数によって与えられます。

|定数|説明|
|--------------|-------------|
|`_IOFBF`|フル バッファリング: `setvbuf` の呼び出しで指定したバッファーが使用され、そのサイズは `setvbuf` の呼び出しで指定したとおりになります。 バッファー ポインターが **NULL** の場合は、指定したサイズで自動的に割り当てられたバッファーが使用されます。|
|`_IOLBF`|`_IOFBF` と同じ。|
|`_IONBF`|`setvbuf` 呼び出しの引数に関係なく、バッファーは使用されません。|

## <a name="see-also"></a>関連項目

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)
