---
description: '詳細については、次を参照してください: __readeflags'
title: __readeflags
ms.date: 09/02/2019
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: e74864f522ba411f44b4a264e9c0e1fd16aa84ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340997"
---
# <a name="__readeflags"></a>__readeflags

**Microsoft 固有の仕様**

プログラムの状態と制御 (EFLAGS) レジスタを読み取ります。

## <a name="syntax"></a>構文

```C
unsigned     int __readeflags(void); /* x86 */
unsigned __int64 __readeflags(void); /* x64 */
```

## <a name="return-value"></a>戻り値

EFLAGS レジスタの値。 戻り値は、32ビットプラットフォームでは32ビット長、64ビットプラットフォームでは64ビット長です。

## <a name="remarks"></a>解説

これらのルーチンは、組み込みとしてのみ使用できます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readeflags`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__writeeflags](../intrinsics/writeeflags.md)
