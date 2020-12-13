---
description: '詳細については、次を参照してください: _InterlockedAddLargeStatistic'
title: _InterlockedAddLargeStatistic
ms.date: 09/02/2019
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: 52ca32d0f9b08d638a66923f8f0204eb515b447e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336875"
---
# <a name="_interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Microsoft 固有の仕様**

最初のオペランドが64ビット値である、インタロックされた加算を実行します。

## <a name="syntax"></a>構文

```C
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

### <a name="parameters"></a>パラメーター

*加数*\
[入力、出力]追加操作の最初のオペランドへのポインター。 が指す値は、加算の結果に置き換えられます。

*値*\
から2番目のオペランド。1番目のオペランドに追加する値。

## <a name="return-value"></a>戻り値

2番目のオペランドの値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_InterlockedAddLargeStatistic`組み込みはアトミックではありません。これは、2つの個別のロックされた命令として実装されるためです。 組み込みのの実行中に別のスレッドで発生したアトミックの64ビット読み取りは、一貫性のない値の読み取りにつながる可能性があります。

`_InterlockedAddLargeStatistic` 読み取り/書き込みのバリアとして動作します。 詳細については、「 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[X86 コンパイラとの競合](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
