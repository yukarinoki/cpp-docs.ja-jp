---
title: プロトタイプ宣言されていない機能 |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c030bd99fc185b3c52535aecb45697672ef4c14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717679"
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