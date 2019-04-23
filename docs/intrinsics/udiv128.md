---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 0e66bbe978199f47134aa288bdd2bac4eb3e332a
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982441"
---
# <a name="udiv128"></a>_udiv128

`_udiv128`組み込み 64 ビット符号なし整数では、128 ビット符号なし整数を除算します。 戻り値の商を保持して、組み込みのポインター パラメーターを通じて剰余を返します。 `_udiv128` **Microsoft 固有の仕様**します。

## <a name="syntax"></a>構文

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>パラメーター

*highDividend* \
[in]被除数の上位 64 ビット。

*lowDividend* \
[in]被除数の下位 64 ビット。

*除数* \
[in]除算する 64 ビット整数。

*remainder* \
[out]残りの 64 ビット整数のビットです。

## <a name="return-value"></a>戻り値

商の 64 ビット。

## <a name="remarks"></a>Remarks

128 ビット被除数の上限の 64 ビットを渡す*highDividend*との下位 64 ビット*lowDividend*します。 組み込みのでは、この値を除算する*除数*します。 残りの部分が指す 64 ビット符号なし整数に格納*剰余*、し、商の 64 ビットを返します。

`_udiv128`組み込みは、Visual Studio 2019 RTM 以降で利用可能です。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|Header|
|---------------|------------------|------------|
|`_udiv128`|X64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_div128](div128.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
