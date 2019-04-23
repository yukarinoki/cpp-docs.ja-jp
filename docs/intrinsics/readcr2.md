---
title: __readcr2
ms.date: 11/04/2016
f1_keywords:
- __readcr2
helpviewer_keywords:
- __readcr2 intrinsic
ms.assetid: d02c97d8-1953-46e7-a79e-a781e2c5bf27
ms.openlocfilehash: e26ccbb3db1dfc113f84210314379b06dae93542
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031103"
---
# <a name="readcr2"></a>__readcr2

**Microsoft 固有の仕様**

CR2 レジスタを読み取り、その値を返します。

## <a name="syntax"></a>構文

```
unsigned __int64 __readcr2(void);
```

## <a name="return-value"></a>戻り値

CR2 レジスタの値。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readcr2`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)