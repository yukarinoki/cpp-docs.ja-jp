---
title: MMWORD |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7314c6d0861195e312c7f72481d2e195e041965d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679235"
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
    movq     mm0, mmword ptr [ebx]
```