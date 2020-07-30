---
title: ilogb、ilogbf、ilogbl2
ms.date: 04/05/2018
api_name:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
ms.openlocfilehash: 6feea7a242a066f669429944226f4ca6022505b6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232522"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb、ilogbf、ilogbl

指定した値を、バイアスをかけない 2 進数の指数として表す整数を取得します。

## <a name="syntax"></a>構文

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
指定した値。

## <a name="return-value"></a>戻り値

成功した場合は、 *x*の底2の指数を値として返し **`signed int`** ます。

それ以外の場合は、で定義されている次のいずれかの値を返し \<math.h> ます。

|入力|結果|
|-----------|------------|
|±0|FP_ILOGB0|
|± inf、± nan、不定|FP_ILOGBNAN|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す**ilogb**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 **ilogb**は常にを受け取り、を返し **`double`** ます。

この関数の呼び出しは、同等の**logb**関数を呼び出し、戻り値をにキャストすることと似てい **`int`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**ilogb**、 **ilogbf**、 **ilogbl**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb、logbf、logbl、_logb、_logbf](logb-logbf-logbl-logb-logbf.md)<br/>
