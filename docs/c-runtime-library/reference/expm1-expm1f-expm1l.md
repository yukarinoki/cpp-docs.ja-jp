---
title: expm1、expm1f、expm1l
ms.date: 04/05/2018
api_name:
- expm1l
- expm1
- expm1f
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 63e984f2228ac6896cd9d2ea959b491565bfb8d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234134"
---
# <a name="expm1-expm1f-expm1l"></a>expm1、expm1f、expm1l

e を底とする値のべき乗から 1 を引く計算を行います。

## <a name="syntax"></a>構文

```C
double expm1(
   double x
);
float expm1(
   float x
);  // C++ only
long double expm1(
   long double x
);  // C++ only
float expm1f(
   float x
);
long double expm1l(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点の指数値。

## <a name="return-value"></a>戻り値

**Expm1**関数は、成功した場合は、e<sup>x</sup> -1 を表す浮動小数点値を返します。 オーバーフローの場合、 **expm1**は**HUGE_VAL**を返し **、HUGE_VALF** **expm1f**はを返します。 **expm1l**は**HUGE_VALL**を返し、 **errno**は**ERANGE**に設定されます。 リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、およびの値を受け取って返す**expm1**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 **expm1**は常にを受け取り、を返し **`double`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**expm1**、 **expm1f**、 **expm1l**|\<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[exp2、exp2f、exp2l](exp2-exp2f-exp2l.md)<br/>
[pow、powf、powl](pow-powf-powl.md)<br/>
