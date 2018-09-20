---
title: _ _mulh |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __mulh
dev_langs:
- C++
helpviewer_keywords:
- __mulh intrinsic
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9393026814e8f3f7dd90704cd08ea96dfb9a35a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407323"
---
# <a name="mulh"></a>__mulh

**Microsoft 固有の仕様**

2 つの 64 ビット符号付き整数の積の上位 64 ビットを返します。

## <a name="syntax"></a>構文

```
__int64 __mulh( 
   __int64 a, 
   __int64 b 
);
```

#### <a name="parameters"></a>パラメーター

*a*<br/>
[in]乗算する最初の数値。

*b*<br/>
[in]乗算する 2 番目の数値。

## <a name="return-value"></a>戻り値

乗算で得られる 128 ビットの結果の上位 64 ビット。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__mulh`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
// mulh.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__mulh)

int main()
{
    __int64 a = 0x0fffffffffffffffI64;
    __int64 b = 0xf0000000I64;

    __int64 result = __mulh(a, b); // the high 64 bits
    __int64 result2 = a * b; // the low 64 bits

    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",
             a, b, result, result2);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)