---
description: '詳細については、次を参照してください: __wbinvd'
title: __wbinvd
ms.date: 09/02/2019
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: b40e1b618e49ab317a7b9cdeea647bcd58df7912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257265"
---
# <a name="__wbinvd"></a>__wbinvd

**Microsoft 固有の仕様**

書き戻しを生成し、Cache () 命令を無効にし `wbinvd` ます。

## <a name="syntax"></a>構文

```C
void __wbinvd(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__wbinvd`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

この関数は、特権レベル (CPL) が0のカーネルモードでのみ使用でき、ルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
