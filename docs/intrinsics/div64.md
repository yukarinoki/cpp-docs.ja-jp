---
title: _div64
ms.date: 04/17/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: a221cc7cf0655a41873c6777aecd8a9b27131b74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62264115"
---
# <a name="div64"></a>_div64

`_div64`組み込みに 32 ビット整数で 64 ビット整数を除算します。 戻り値の商を保持して、組み込みのポインター パラメーターを通じて剰余を返します。 `_div64` **Microsoft 固有の仕様**します。

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
[in]分割する 64 ビット整数。

*除数* \
[in]除算する 32 ビット整数。

*remainder* \
[out]残りの部分の 32 ビット整数のビットです。

## <a name="return-value"></a>戻り値

商の 32 ビットです。

## <a name="remarks"></a>Remarks

`_div64`組み込み除算*被除数*によって*除数*します。 残りの部分が指す 32 ビット整数に格納*剰余*、し、商の 32 ビットを返します。

`_div64`組み込みは、Visual Studio 2019 RTM 以降で利用可能です。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|Header|
|---------------|------------------|------------|
|`_div64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_udiv64](udiv64.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
