---
description: 詳細については、「isfinite、_finite、_finitef」を参照してください。
title: isfinite、_finite、_finitef
ms.date: 01/31/2019
api_name:
- _finite
- _finitef
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- isfinite
- finite
- _finite
- _finitef
- math/isfinite
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: ef0747c88d62445c1cbd31f5c7afe6a651f50880
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263115"
---
# <a name="isfinite-_finite-_finitef"></a>isfinite、_finite、_finitef

浮動小数点値が有限かどうかを決定します。

## <a name="syntax"></a>構文

```C
int isfinite(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isfinite(
   FloatingType x
) throw(); /* C++-only template function */

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

`isfinite` `_finite` `_finitef` *X* が normal または subnormal の有限値の場合、マクロと関数および関数は0以外の値を返します。 引数が無限または NaN の場合は、0を返します。 C++ インラインテンプレート関数は `isfinite` 同じように動作しますが、 **`true`** またはを返し **`false`** ます。

## <a name="remarks"></a>解説

`isfinite` は、C としてコンパイルされた場合はマクロ、C++ としてコンパイルされた場合はインラインテンプレート関数です。 `_finite`関数と `_finitef` 関数は、Microsoft 固有の関数です。 `_finitef` 関数は、x86、ARM、または ARM64 プラットフォーム用にコンパイルするときにのみ使用できます。

## <a name="requirements"></a>要件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float.h> または \<math.h>|\<float.h>、\<math.h>、\<cfloat>、または \<cmath>|
|`isfinite`, `_finitef`|\<math.h>|\<math.h> または \<cmath>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
