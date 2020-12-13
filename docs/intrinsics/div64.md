---
description: '詳細については、次を参照してください: _div64'
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 4c9c8f02f7092c12d5734f96346897e2eca9898a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337071"
---
# <a name="_div64"></a>_div64

組み込みは、 `_div64` 64 ビット整数を32ビット整数で除算します。 戻り値は商を保持し、組み込みはポインターパラメーターを使用して剰余を返します。 `_div64` は **Microsoft 固有** です。

## <a name="syntax"></a>構文

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>パラメーター

*dividend* \
から除算する64ビット整数。

*divisor* \
から除算する32ビット整数。

*後述* \
入出力剰余の32ビット整数ビット。

## <a name="return-value"></a>戻り値

商の32ビット。

## <a name="remarks"></a>解説

`_div64`組み込みは *被除数* を *除数* で除算します。 剰余は *剰余* によって示された32ビット整数に格納され、商の32ビットを返します。

`_div64`組み込みは、Visual Studio 2019 RTM 以降で使用できます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|ヘッダー|
|---------------|------------------|------------|
|`_div64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_udiv64](udiv64.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
