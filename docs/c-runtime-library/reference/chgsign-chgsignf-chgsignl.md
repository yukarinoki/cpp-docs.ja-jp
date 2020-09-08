---
title: _chgsign、_chgsignf、_chgsignl
description: _Chgsign、_chgsignf、および _chgsignl の API リファレンスこれにより、浮動小数点引数の符号が反転されます。
ms.date: 04/05/2018
api_name:
- _chgsignl
- _chgsign
- _chgsignf
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
- _chgsignf
- chgsign
- _chgsignl
- _chgsign
helpviewer_keywords:
- _chgsignl function
- _chgsignf function
- chgsign function
- _chgsign function
ms.assetid: a6646f8e-213d-4564-8617-f43bc66f989f
ms.openlocfilehash: 7dc934f3c2d22cc36abe5f31f7d64e0674ccdd3a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555203"
---
# <a name="_chgsign-_chgsignf-_chgsignl"></a>_chgsign、_chgsignf、_chgsignl

浮動小数点引数の符号を反転させます。

## <a name="syntax"></a>構文

```C
double _chgsign(
   double x
);
float _chgsignf(
   float x
);
long double _chgsignl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
変更する浮動小数点値。

## <a name="return-value"></a>戻り値

**_Chgsign**関数は、浮動小数点引数*x*と等しいが、符号が反転された値を返します。 エラーの戻り値はありません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_chgsign**|\<float.h>|
|**_chgsignf**、 **_chgsignl**|\<math.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
[copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl](copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)<br/>
