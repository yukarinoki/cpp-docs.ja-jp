---
title: プロトタイプ宣言されていない関数
ms.date: 11/04/2016
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
ms.openlocfilehash: 38207be6111dadc338593e55b683b88e0480e1ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633429"
---
# <a name="unprototyped-functions"></a>プロトタイプ宣言されていない関数

関数の完全なプロトタイプではない場合、呼び出し元は整数値として整数と浮動小数点値として渡す倍精度。 浮動小数点値の場合にのみ、整数レジスタと浮動小数点レジスタの両方が含まれている浮動小数点値場合は、呼び出し先は、整数レジスタに値が必要です。

```
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)