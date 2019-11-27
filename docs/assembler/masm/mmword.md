---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: d4378c1435df09f249fe7f55dabd4bd0f43f6100
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397174"
---
# <a name="mmword"></a>MMWORD

MMX および SSE (XMM) 命令で64ビットのマルチメディアオペランドに使用されます。

## <a name="syntax"></a>構文

> **MMWORD**

## <a name="remarks"></a>コメント

**Mmword**は型です。  **Mmword**が MASM に追加される前に、同等の機能がによって実現されました。

```asm
    mov mm0, qword ptr [ebx]
```

どちらの命令も64ビットオペランドで動作しますが、 **QWORD**は64ビット符号なし整数の型であり、 **mmword**は64ビットマルチメディア値の型です。

**Mmword**は[__m64](../../cpp/m64.md)と同じ型を表すことを目的としています。

## <a name="example"></a>例

```asm
    movq     mm0, mmword ptr [ebx]
```
