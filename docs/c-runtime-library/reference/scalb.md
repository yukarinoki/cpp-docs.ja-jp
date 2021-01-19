---
description: '詳細については、次を参照してください: _scalb、_scalbf'
title: _scalb、_scalbf
ms.date: 1/15/2021
api_name:
- _scalb
- _scalbf
- _o__scalb
- _o__scalbf
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- scalb
- _scalb
- _scalbf
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.openlocfilehash: da5a33bd6ed24ba0a3a58f789a9c8900910454d1
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564083"
---
# <a name="_scalb-_scalbf"></a>`_scalb`, `_scalbf`

引数を 2 のべき乗の倍率で増減させます。

## <a name="syntax"></a>構文

```C
double _scalb(
   double x,
   long exp
);
float _scalbf(
   float x,
   long exp
); /* x64 only */
```

### <a name="parameters"></a>パラメーター

*`x`*\
倍精度浮動小数点値。

*`exp`*\
長整数型の指数。

## <a name="return-value"></a>戻り値

正常終了した場合は指数値が返されます。 オーバーフローが発生した場合 (の符号によって異なり *`x`* ます)、は **`_scalb`** +/-を返し **`HUGE_VAL`** **`errno`** ます。変数はに設定され **`ERANGE`** ます。

このリターン コードとその他のリターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>注釈

関数は、 **`_scalb`** 値2を計算し *`x`* \* <sup>*`exp`*</sup> ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`_scalb`**, **`_scalbf`**|`<float.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`ldexp`](ldexp.md)