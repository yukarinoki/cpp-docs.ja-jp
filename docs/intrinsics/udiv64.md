---
title: _udiv64
ms.date: 04/17/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 73a29b180eeda49a9a25e9e568d25c7563234fad
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982451"
---
# <a name="udiv64"></a>_udiv64

`_udiv64`組み込みに 32 ビット符号なし整数が 64 ビット符号なし整数を除算します。 戻り値の商を保持して、組み込みのポインター パラメーターを通じて剰余を返します。 `_udiv64` **Microsoft 固有の仕様**します。

## <a name="syntax"></a>構文

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>パラメーター

*被除数*<br/>
[in]分割する 64 ビット符号なし整数。

*除数*<br/>
[in]除算する 32 ビット符号なし整数。

*remainder*<br/>
[out]32 ビット符号なし整数の剰余。

## <a name="return-value"></a>戻り値

商の 32 ビットです。

## <a name="remarks"></a>Remarks

`_udiv64`組み込み除算*被除数*によって*除数*します。 残りの部分が指す 32 ビット符号なし整数に格納*剰余*、し、商の 32 ビットを返します。

`_udiv64`組み込みは、Visual Studio 2019 RTM 以降で利用可能です。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|Header|
|---------------|------------------|------------|
|`_udiv64`|x86、x64|\<immintrin.h>|

## <a name="see-also"></a>関連項目

[_div64](div64.md) \
[コンパイラの組み込み](compiler-intrinsics.md)
