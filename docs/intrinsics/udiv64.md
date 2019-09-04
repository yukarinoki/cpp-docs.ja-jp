---
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 6dabbc94260ef578eb1a58a1b289b4a4654decdd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219680"
---
# <a name="_udiv64"></a>_udiv64

組み込み`_udiv64`は、64ビット符号なし整数を32ビット符号なし整数で除算します。 戻り値は商を保持し、組み込みはポインターパラメーターを使用して剰余を返します。 `_udiv64`は**Microsoft 固有**のものです。

## <a name="syntax"></a>構文

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>パラメーター

*被除数*\
から除算する64ビット符号なし整数。

*公約数*\
からによって除算される32ビット符号なし整数。

*後述*\
入出力32ビット符号なし整数の剰余。

## <a name="return-value"></a>戻り値

商の32ビット。

## <a name="remarks"></a>Remarks

組み込み`_udiv64`は*被除数*を*除数*で除算します。 剰余が*剰余*によって示された32ビット符号なし整数に格納し、商の32ビットを返します。

組み込み`_udiv64`は、Visual Studio 2019 RTM 以降で使用できます。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|Header|
|---------------|------------------|------------|
|`_udiv64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_div64](div64.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
