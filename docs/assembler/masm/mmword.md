---
title: MMWORD
ms.date: 08/30/2018
f1_keywords:
- MMWORD
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
ms.openlocfilehash: 1205338f9140c74a3a6e0b4bce57983edc80862e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541119"
---
# <a name="mmword"></a>MMWORD

MMX と SSE (XMM) の手順で、64 ビット マルチ メディア オペランドに使用されます。

## <a name="syntax"></a>構文

> MMWORD

## <a name="remarks"></a>Remarks

`MMWORD` 型です。  MMWORD MASM に追加されている、前に同等の機能を獲得しましたでした。

```asm
    mov mm0, qword ptr [ebx]
```

両方の手順については、64 ビットのオペランドで作業中に`QWORD`は 64 ビット符号なし整数の型と`MMWORD`は 64 ビットのマルチ メディア値の型です。

`MMWORD` 同じ型を表すために、 [_ _m64](../../cpp/m64.md)します。

## <a name="example"></a>例

```asm
    movq     mm0, mmword ptr [ebx]
```