---
title: コンパイラ エラー C3415
ms.date: 11/04/2016
f1_keywords:
- C3415
helpviewer_keywords:
- C3415
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
ms.openlocfilehash: 3d4163fac83e24d30f29aed92e7a1ec1fc9e362f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482005"
---
# <a name="compiler-error-c3415"></a>コンパイラ エラー C3415

異なる属性 ('value') を持つ、複数の 'section_name' セクションが見つかりました

競合する値が [section](../../preprocessor/section.md) プラグマで指定されました。

`value` は、ntimage.h で指定された、セクションの現在の設定です。 例えば:

```
// Section contains extended relocations.
#define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000
// Section can be discarded.
#define IMAGE_SCN_MEM_DISCARDABLE            0x02000000
// Section is not cachable.
#define IMAGE_SCN_MEM_NOT_CACHED             0x04000000
// Section is not pageable.
#define IMAGE_SCN_MEM_NOT_PAGED              0x08000000
// Section is shareable.
#define IMAGE_SCN_MEM_SHARED                 0x10000000
// Section is executable.
#define IMAGE_SCN_MEM_EXECUTE                0x20000000
// Section is readable.
#define IMAGE_SCN_MEM_READ                   0x40000000
// Section is writeable.
#define IMAGE_SCN_MEM_WRITE                  0x80000000
```

次の例では C3415 が生成されます。

```
// C3415.cpp
#pragma section("mysec1",write)
#pragma section("mysec1",read)   // C3415
```