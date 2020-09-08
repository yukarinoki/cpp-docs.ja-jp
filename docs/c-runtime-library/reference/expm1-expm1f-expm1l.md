---
title: expm1、expm1f、expm1l
description: Expm1、expm1f、および expm1 の API リファレンスこれにより、底 e の値の指数から1を引いた値が計算されます。
ms.date: 9/1/2020
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
ms.openlocfilehash: 6d352e91d895cd63c7134faff90bc1bc43a50708
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556503"
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
#define expm1(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
浮動小数点の指数値。

## <a name="return-value"></a>戻り値

**Expm1**関数は、成功した場合は、e<sup>x</sup> -1 を表す浮動小数点値を返します。 オーバーフローの場合、 **expm1**は**HUGE_VAL**を返し **、HUGE_VALF** **expm1f**はを返します。 **expm1l**は**HUGE_VALL**を返し、 **errno**は**ERANGE**に設定されます。 リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、およびの値を受け取って返す **expm1** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **expm1** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `expm1()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**expm1**、 **expm1f**、 **expm1l**|\<math.h>|
|**expm1** マクロ | \<tgmath.h> |

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[exp2、exp2f、exp2l](exp2-exp2f-exp2l.md)<br/>
[pow、powf、powl](pow-powf-powl.md)<br/>
