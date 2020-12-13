---
description: '詳細情報: MMWORD'
title: MMWORD
ms.date: 12/17/2019
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: f0e888efcfea7c1ca94129ff3e4cd2f40644ae13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128234"
---
# <a name="mmword"></a>MMWORD

MMX および SSE (XMM) 命令で64ビットのマルチメディアオペランドに使用されます。

## <a name="syntax"></a>構文

> **MMWORD**

## <a name="remarks"></a>解説

**Mmword** は型です。  **Mmword** が MASM に追加される前に、同等の機能がによって実現されました。

```asm
    mov mm0, qword ptr [ebx]
```

どちらの命令も64ビットオペランドで動作しますが、 **QWORD** は64ビット符号なし整数の型であり、 **mmword** は64ビットマルチメディア値の型です。

**Mmword** は [__m64](../../cpp/m64.md)と同じ型を表すことを目的としています。

## <a name="example"></a>例

```asm
    movq     mm0, mmword ptr [ebx]
```

## <a name="see-also"></a>参照

[MASM BNF 文法](masm-bnf-grammar.md)
