---
title: _finite、_finitef
ms.date: 04/05/2018
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: 7b1bce6f1b2da77ed9de255f49dd8d0160e33e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431664"
---
# <a name="finite-finitef"></a>_finite、_finitef

浮動小数点値が有限かどうかを決定します。

## <a name="syntax"></a>構文

```C
int _finite(
   double x
);

int _finitef(
   float x
); /* x64 and ARM/ARM64 only */
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

両方 **_finite**と **_finitef**場合は、0 以外の値を返す引数*x*は有限; である場合は、-INF < *x* < + INF。 引数が無限または NAN の場合は、0 を返します。

## <a name="remarks"></a>Remarks

**_Finite**と **_finitef**関数は、Microsoft 固有の仕様。 **_Finitef**関数は x86、ARM、または ARM64 プラットフォームで利用可能な場合にコンパイルのみ。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------------|-------------------------------|
|**_finite**|\<float.h> または \<math.h>|\<float.h>、\<math.h>、\<cfloat>、または \<cmath>|
|**_finitef**|\<math.h>|\<math.h> または \<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
