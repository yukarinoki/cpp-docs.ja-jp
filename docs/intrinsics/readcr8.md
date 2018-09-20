---
title: _ _readcr8 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readcr8
dev_langs:
- C++
helpviewer_keywords:
- __readcr8 intrinsic
ms.assetid: fce16953-87ff-4fbe-8081-7962b97ae46c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0509f7e344e29397aa1dac592d1a898c9d9cdf60
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395498"
---
# <a name="readcr8"></a>__readcr8

**Microsoft 固有の仕様**

CR8 レジスタを読み取り、その値を返します。

## <a name="syntax"></a>構文

```
unsigned __int64 __readcr8(void);
```

## <a name="return-value"></a>戻り値

CR8 レジスタの値。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__readcr8`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)