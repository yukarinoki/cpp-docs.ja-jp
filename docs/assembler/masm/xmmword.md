---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: a248c9318764cd632fed2afd8481ee2b2102fe31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479783"
---
# <a name="xmmword"></a>XMMWORD

MMX と SSE (XMM) の手順では、128 ビットのマルチ メディア オペランドに使用されます。

## <a name="syntax"></a>構文

> XMMWORD

## <a name="remarks"></a>Remarks

`XMMWORD` 同じ型を表すために、 [_ _m128](../../cpp/m128.md)します。

## <a name="example"></a>例

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```