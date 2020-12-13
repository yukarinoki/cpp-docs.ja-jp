---
description: '詳細については、次を参照してください: __readcr8'
title: __readcr8
ms.date: 09/02/2019
f1_keywords:
- __readcr8
helpviewer_keywords:
- __readcr8 intrinsic
ms.assetid: fce16953-87ff-4fbe-8081-7962b97ae46c
ms.openlocfilehash: 1961f00575956c8377131cd0871e59f79db5dc1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341023"
---
# <a name="__readcr8"></a>__readcr8

**Microsoft 固有の仕様**

CR8 register を読み取り、その値を返します。

## <a name="syntax"></a>構文

```C
unsigned __int64 __readcr8(void);
```

## <a name="return-value"></a>戻り値

CR8 レジスタの値。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__readcr8`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みはカーネルモードでのみ使用でき、ルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
