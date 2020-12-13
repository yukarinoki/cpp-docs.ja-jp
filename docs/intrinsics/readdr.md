---
description: '詳細については、次を参照してください: __readdr'
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: b3b5952d940db91b278344ab45edb3e8b914c094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341010"
---
# <a name="__readdr"></a>__readdr

**Microsoft 固有の仕様**

指定されたデバッグレジスタの値を読み取ります。

## <a name="syntax"></a>構文

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>パラメーター

*DebugRegister*\
からデバッグレジスタを識別する 0 ~ 7 の定数。

## <a name="return-value"></a>戻り値

指定されたデバッグレジスタの値。

## <a name="remarks"></a>解説

これらの組み込みはカーネルモードでのみ使用でき、ルーチンは組み込みとしてのみ使用できます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readdr`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
