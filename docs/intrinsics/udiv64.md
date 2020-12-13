---
description: '詳細については、次を参照してください: _udiv64'
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 21f383cd78885ab8d3d8bb66a87623a73b59ff95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333645"
---
# <a name="_udiv64"></a>_udiv64

組み込みは、 `_udiv64` 64 ビット符号なし整数を32ビット符号なし整数で除算します。 戻り値は商を保持し、組み込みはポインターパラメーターを使用して剰余を返します。 `_udiv64` は **Microsoft 固有** です。

## <a name="syntax"></a>構文

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>パラメーター

*dividend*\
から除算する64ビット符号なし整数。

*divisor*\
からによって除算される32ビット符号なし整数。

*後述*\
入出力32ビット符号なし整数の剰余。

## <a name="return-value"></a>戻り値

商の32ビット。

## <a name="remarks"></a>解説

`_udiv64`組み込みは *被除数* を *除数* で除算します。 剰余が *剰余* によって示された32ビット符号なし整数に格納し、商の32ビットを返します。

`_udiv64`組み込みは、Visual Studio 2019 RTM 以降で使用できます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|ヘッダー|
|---------------|------------------|------------|
|`_udiv64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_div64](div64.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
