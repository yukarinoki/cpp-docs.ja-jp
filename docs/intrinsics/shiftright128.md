---
description: '詳細については、次を参照してください: __shiftright128'
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: 71f8a0d9b740ebfef5e930715e07d1ec31950269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306977"
---
# <a name="__shiftright128"></a>__shiftright128

**Microsoft 固有の仕様**

64 ビットの 2 つの数 `LowPart` および `HighPart` で表される 128 ビットの数を、`Shift` で指定されたビット数だけ右にシフトし、結果の下位 64 ビットを返します。

## <a name="syntax"></a>構文

```C
unsigned __int64 __shiftright128(
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

結果の下位 64 ビット。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__shiftright128`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`Shift` の値は常にモジュロ 64 です。このため、たとえば `__shiftright128(0, 1, 64)` をコールすると、上位部分が `0` ビット右にシフトされ、下位部分である `0` が返されます。`1` ではありません。

## <a name="example"></a>例

例については、「 [__shiftleft128](../intrinsics/shiftleft128.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__shiftleft128](../intrinsics/shiftleft128.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
