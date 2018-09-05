---
title: XMMWORD |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fbb578c5e168f53bc1b4e217713efa1ea329743
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689215"
---
# <a name="xmmword"></a>XMMWORD

MMX と SSE (XMM) の手順では、128 ビットのマルチ メディア オペランドに使用されます。

## <a name="syntax"></a>構文

> XMMWORD

## <a name="remarks"></a>Remarks

`XMMWORD` 同じ型を表すために、 [_ _m128](../../cpp/m128.md)します。

## <a name="example"></a>例

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```