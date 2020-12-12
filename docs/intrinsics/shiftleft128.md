---
description: '詳細については、次を参照してください: __shiftleft128'
title: __shiftleft128
ms.date: 09/02/2019
f1_keywords:
- __shiftleft128
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
ms.openlocfilehash: e0e1402660c2ddb6f5993e5186302ff489ed864f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306990"
---
# <a name="__shiftleft128"></a>__shiftleft128

**Microsoft 固有の仕様**

64 ビットの 2 つの数 `LowPart` および `HighPart` で表される 128 ビットの数を、`Shift` で指定されたビット数だけ左にシフトし、結果の上位 64 ビットを返します。

## <a name="syntax"></a>構文

```C
unsigned __int64 __shiftleft128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>パラメーター

*LowPart*\
からシフトする128ビット数量の下位64ビット。

*Largeint.highpart*\
からシフトする128ビット数量の上位64ビット。

*転換*\
からシフトするビット数。

## <a name="return-value"></a>戻り値

結果の上位 64 ビット。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__shiftleft128`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

*シフト* 値は常にモジュロ64であるため、たとえば、を呼び出すと、 `__shiftleft128(1, 0, 64)` 関数は低位部分のビットを左にシフト `0` し、の大部分を返しますが、それ以外の場合はを返し `0` `1` ます。

## <a name="example"></a>例

```C
// shiftleft128.c
// processor: IPF, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__shiftleft128, __shiftright128)

int main()
{
    unsigned __int64 i = 0x1I64;
    unsigned __int64 j = 0x10I64;
    unsigned __int64 ResultLowPart;
    unsigned __int64 ResultHighPart;

    ResultLowPart = i << 1;
    ResultHighPart = __shiftleft128(i, j, 1);

    // concatenate the low and high parts padded with 0's
    // to display correct hexadecimal 128 bit values
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);

    ResultHighPart = j >> 1;
    ResultLowPart = __shiftright128(i, j, 1);

    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);
}
```

```Output
0x100000000000000001 << 1 = 0x200000000000000002
0x100000000000000001 >> 1 = 0x080000000000000000
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__shiftright128](../intrinsics/shiftright128.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
