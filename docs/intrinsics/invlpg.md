---
description: '詳細については、次を参照してください: __invlpg'
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 16d8f51c8bf36ea94be7b1325ee5bed256c29693
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167904"
---
# <a name="__invlpg"></a>__invlpg

**Microsoft 固有の仕様**

では、 `invlpg` *アドレス* が指すメモリに関連付けられているページの変換ルックアサイドバッファー (TLB) を無効にする x86 命令が生成されます。

## <a name="syntax"></a>構文

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>パラメーター

*先*\
から64ビットアドレス。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__invlpg`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みは `__invlpg` 特権命令を出力し、特権レベル (CPL) が0のカーネルモードでのみ使用できます。

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
