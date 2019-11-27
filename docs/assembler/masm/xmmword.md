---
title: XMMWORD
ms.date: 08/30/2018
f1_keywords:
- XMMWORD
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
ms.openlocfilehash: c7783049a143b19295a67cd3e9e40afeab3c814f
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74392787"
---
# <a name="xmmword"></a>XMMWORD

MMX および SSE (XMM) 命令で128ビットのマルチメディアオペランドに使用されます。

## <a name="syntax"></a>構文

> **XMMWORD**

## <a name="remarks"></a>コメント

**Xmmword**は[__m128](../../cpp/m128.md)と同じ型を表すことを目的としています。

## <a name="example"></a>例

```asm
    movdqa   xmm0, xmmword ptr [ebx]
```
