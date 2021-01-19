---
description: '詳細については、次を参照してください: _fpclass、_fpclassf'
title: _fpclass、_fpclassf
ms.date: 1/15/2021
api_name:
- _fpclass
- _fpclassf
- _o__fpclass
- _o__fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.openlocfilehash: 3fb97c5aa787c4c102e787fa3b08650f23ca546a
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563992"
---
# <a name="_fpclass-_fpclassf"></a>`_fpclass`, `_fpclassf`

引数の浮動小数点の分類を示す値を返します。

## <a name="syntax"></a>構文

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>パラメーター

*`x`*\
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

**`_fpclass`** 関数および **`_fpclassf`** 関数は、引数の浮動小数点の分類を示す整数値を返し *`x`* ます。 分類には、で定義されている次のいずれかの値を指定でき `<float.h>` ます。

|値|説明|
|-----------|-----------------|
|**`_FPCLASS_SNAN`**|シグナル型 NaN|
|**`_FPCLASS_QNAN`**|クワイエット型 NaN|
|**`_FPCLASS_NINF`**|負の無限大 ( `-INF` )|
|**`_FPCLASS_NN`**|正規化された負の 0 以外の値|
|**`_FPCLASS_ND`**|正規化されない負の値|
|**`_FPCLASS_NZ`**|負のゼロ (-0)|
|**`_FPCLASS_PZ`**|正のゼロ (+0)|
|**`_FPCLASS_PD`**|正規化された正の値|
|**`_FPCLASS_PN`**|正規化された正の 0 以外の値|
|**`_FPCLASS_PINF`**|正の無限大 ( `+INF` )|

## <a name="remarks"></a>注釈

**`_fpclass`** 関数と **`_fpclassf`** 関数は、Microsoft 固有の関数です。 これらはに似 [`fpclassify`](fpclassify.md) ていますが、引数に関するより詳細な情報を返します。 **`_fpclassf`** 関数は、x64 プラットフォーム用にコンパイルされた場合にのみ使用できます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**`_fpclass`**, **`_fpclassf`**|`<float.h>`|

互換性と適合性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`isnan`, `_isnan`, `_isnanf`](isnan-isnan-isnanf.md)\
[`fpclassify`](fpclassify.md)