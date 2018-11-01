---
title: _scalb、_scalbf
ms.date: 04/05/2018
apiname:
- _scalb
- _scalbf
apilocation:
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
apitype: DLLExport
f1_keywords:
- scalb
- _scalb
- _scalbf
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
ms.openlocfilehash: c3f776ec27c365601d4fe57fb6cf0a5c9b9e0cbd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551035"
---
# <a name="scalb-scalbf"></a>_scalb、_scalbf

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

*x*<br/>
倍精度浮動小数点値。

*exp*<br/>
長整数型の指数。

## <a name="return-value"></a>戻り値

正常終了した場合は指数値が返されます。 オーバーフローが発生 (の符号に応じて*x*)、 **_scalb** +/-返します**HUGE_VAL**、 **errno**に変数が設定されている**ERANGE**します。

このリターン コードとその他のリターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

**_Scalb**関数の値を計算*x* \* 2<sup>*exp*</sup>します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_scalb**、 **_scalbf**|\<float.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
