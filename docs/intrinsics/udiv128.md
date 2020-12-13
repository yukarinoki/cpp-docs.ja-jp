---
description: '詳細については、次を参照してください: _udiv128'
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: f88546a179106f4291fcaeb865f1aad9e67c4045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333656"
---
# <a name="_udiv128"></a>_udiv128

組み込みは、 `_udiv128` 128 ビット符号なし整数を64ビット符号なし整数で除算します。 戻り値は商を保持し、組み込みはポインターパラメーターを使用して剰余を返します。 `_udiv128` は **Microsoft 固有** です。

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
から被除数の上位64ビット。

*lowDividend* \
から被除数の下位64ビット。

*divisor* \
から除算する64ビット整数。

*後述* \
入出力剰余の64ビット整数ビット。

## <a name="return-value"></a>戻り値

商の64ビット。

## <a name="remarks"></a>解説

128ビット被除数の上位64ビットを *Highdividend* に、低い64ビットを *lowdividend* に渡します。 組み込みは、この値を *除数* で除算します。 剰余が *剰余* によって示された64ビット符号なし整数に格納し、商の64ビットを返します。

`_udiv128`組み込みは、Visual Studio 2019 RTM 以降で使用できます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|ヘッダー|
|---------------|------------------|------------|
|`_udiv128`|X64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_div128](div128.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
