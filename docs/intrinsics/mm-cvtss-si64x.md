---
title: _mm_cvtss_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: 259e3933c831ba685fa9d00d0f6471975a31f2cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606844"
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x

**Microsoft 固有の仕様**

拡張 x64 を生成、変換スカラー単一単精度浮動小数点数を 64 ビット整数のバージョン (`cvtss2si`) 命令。

## <a name="syntax"></a>構文

```
__int64 _mm_cvtss_si64x( 
   __m128 value 
);
```

#### <a name="parameters"></a>パラメーター

*値*<br/>
[in]`__m128`浮動小数点値を含む構造体。

## <a name="return-value"></a>戻り値

64 ビット整数の場合、最初の浮動小数点値の整数値への変換の結果。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_mm_cvtss_si64x`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

構造体の値の最初の要素が整数に変換し、返されます。 MXCSR で丸め制御ビットを使用すると、丸め処理を決定します。 既定の丸めモードは、小数部分が 0.5 の場合、偶数丸められる最も近い round をします。 `__m128`構造は、この組み込みは、XMM レジスタの値、XMM レジスタを表すし、システム メモリに書き込みます。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
// _mm_cvtss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] =
                           { 101.25, 200.75, 300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvtss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__m128d](../cpp/m128d.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)