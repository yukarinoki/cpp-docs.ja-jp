---
title: _ _readeflags |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readeflags
dev_langs:
- C++
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d32096f50561ad89b2c9fdc50ca3c7e00425bf86
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447597"
---
# <a name="readeflags"></a>__readeflags

プログラムのステータスと制御 (空文) の登録を読み取ります。

## <a name="syntax"></a>構文

```
unsigned     int __readeflags(void);
unsigned __int64 __readeflags(void);
```

## <a name="return-value"></a>戻り値

立てるレジスタの値。 戻り値は 32 ビット、32 ビット プラットフォームでは長と 64 ビット、64 ビット プラットフォームでは長。

## <a name="remarks"></a>Remarks

これらのルーチンは組み込みとしてのみ使用できます。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readeflags`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__writeeflags](../intrinsics/writeeflags.md)