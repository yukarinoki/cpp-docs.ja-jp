---
description: '詳細については、次を参照してください: _bittestandreset、_bittestandreset64'
title: _bittestandreset、_bittestandreset64
ms.date: 09/02/2019
f1_keywords:
- _bittestandreset64_cpp
- _bittestandreset
- _bittestandreset_cpp
- _bittestandreset64
helpviewer_keywords:
- btr instruction
- _bittestandreset intrinsic
- _bittestandreset64 intrinsic
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
ms.openlocfilehash: 5d0b6133b981a7008bbe4979ee123cebd5ef99fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337177"
---
# <a name="_bittestandreset-_bittestandreset64"></a>_bittestandreset、_bittestandreset64

**Microsoft 固有の仕様**

アドレスのビットを確認する命令を生成し `b` `a` 、その現在の値を返し、ビットを0にリセットします。

## <a name="syntax"></a>構文

```C
unsigned char _bittestandreset(
   long *a,
   long b
);
unsigned char _bittestandreset64(
   __int64 *a,
   __int64 b
);
```

### <a name="parameters"></a>パラメーター

*ある*\
[入力、出力]検査するメモリへのポインター。

*b*\
からテストするビット位置。

## <a name="return-value"></a>戻り値

指定した位置にあるビット。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_bittestandreset`|x86、ARM、x64、ARM64|
|`_bittestandreset64`|x64、ARM64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```cpp
// bittestandreset.cpp
// processor: x86, IPF, x64
#include <stdio.h>
#include <limits.h>
#include <intrin.h>

#pragma intrinsic(_bittestandreset)

// Check the sign bit and reset to 0 (taking the absolute value)
// Returns 0 if the number is positive or zero
// Returns 1 if the number is negative
unsigned char absolute_value(long* p)
{
   const int SIGN_BIT = 31;
   return _bittestandreset(p, SIGN_BIT);
}

int main()
{
    long i = -112;
    unsigned char result;

    // Check the sign bit and reset to 0 (taking the absolute value)

    result = absolute_value(&i);
    if (result == 1)
        printf_s("The number was negative.\n");
}
```

```Output
The number was negative.
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
