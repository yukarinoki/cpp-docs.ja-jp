---
description: '詳細については、次を参照してください: __int2c'
title: __int2c
ms.date: 09/02/2019
f1_keywords:
- __int2c
- __int2c_cpp
helpviewer_keywords:
- int2c intrinsic
- int 2c instruction
- __int2c intrinsic
ms.assetid: aa20ff30-adef-42bb-8577-8010f3122f8e
ms.openlocfilehash: 0ca1cc4d998a6e144d1d172f02ec8b9aa4c739e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336904"
---
# <a name="__int2c"></a>__int2c

**Microsoft 固有の仕様**

割り込みを `int 2c` トリガーする命令を生成し `2c` ます。

## <a name="syntax"></a>構文

```C
void __int2c(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__int2c`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
