---
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 1d05c5d6e25540a5de1b2f8231697c9a738759ce
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216764"
---
# <a name="_div64"></a>_div64

組み込み`_div64`は、64ビット整数を32ビット整数で除算します。 戻り値は商を保持し、組み込みはポインターパラメーターを使用して剰余を返します。 `_div64`は**Microsoft 固有**のものです。

## <a name="syntax"></a>構文

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>パラメーター

*被除数* \
から除算する64ビット整数。

*公約数* \
から除算する32ビット整数。

*後述* \
入出力剰余の32ビット整数ビット。

## <a name="return-value"></a>戻り値

商の32ビット。

## <a name="remarks"></a>Remarks

組み込み`_div64`は*被除数*を*除数*で除算します。 剰余は*剰余*によって示された32ビット整数に格納され、商の32ビットを返します。

組み込み`_div64`は、Visual Studio 2019 RTM 以降で使用できます。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|Header|
|---------------|------------------|------------|
|`_div64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_udiv64](udiv64.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
