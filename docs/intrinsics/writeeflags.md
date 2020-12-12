---
description: '詳細については、次を参照してください: __writeeflags'
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 9c439194782f52b474ec6c6365705ebd8756c6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331867"
---
# <a name="__writeeflags"></a>__writeeflags

**Microsoft 固有の仕様**

指定した値をプログラムの状態と制御 (EFLAGS) レジスタに書き込みます。

## <a name="syntax"></a>構文

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>パラメーター

*値*\
からEFLAGS レジスタに書き込む値。 `Value`パラメーターは32ビットプラットフォームの場合は32ビット長、64ビットプラットフォームの場合は64ビット長です。

## <a name="remarks"></a>解説

これらのルーチンは、組み込みとしてのみ使用できます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__writeeflags`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
