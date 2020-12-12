---
description: '詳細情報: XMMWORD'
title: XMMWORD
ms.date: 12/17/2019
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: 304ac53a29fa7912107d6d4e87ee6efd3924ac3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124983"
---
# <a name="xmmword"></a>XMMWORD

MMX および SSE (XMM) 命令で128ビットのマルチメディアオペランドに使用されます。

## <a name="syntax"></a>構文

> **XMMWORD**

## <a name="remarks"></a>解説

**Xmmword** は [__m128](../../cpp/m128.md)と同じ型を表すことを目的としています。

## <a name="example"></a>例

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```

## <a name="see-also"></a>参照

[MASM BNF 文法](masm-bnf-grammar.md)
