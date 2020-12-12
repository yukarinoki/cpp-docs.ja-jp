---
description: '詳細については、次を参照してください: _mm_cvttss_si64x'
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: a4af7b726d0f15099586bc94348ab4ba7ebf5b8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167631"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Microsoft 固有の仕様**

切り捨てを使用した変換の x64 拡張バージョンを出力し Single-Precision Floating-Point Number を64ビット整数 () 命令に変換し `cvttss2si` ます。

## <a name="syntax"></a>構文

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>パラメーター

*数値*\
から **`__m128`** 単精度浮動小数点値を含む構造体。

## <a name="return-value"></a>戻り値

最初の浮動小数点値を64ビット整数に変換した結果。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みは、 `_mm_cvtss_si64x` 不正確な変換が0方向に切り捨てられた場合にのみ異なります。 構造体は XMM register を表しているため、 **`__m128`** 生成された命令は XMM レジスタからシステムメモリにデータを移動します。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```cpp
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__m128](../cpp/m128.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
