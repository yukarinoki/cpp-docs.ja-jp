---
description: '詳細情報: fpclassify'
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: 716684f15e82fb439c16239a61401b892a244f93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164836"
---
# <a name="fpclassify"></a>fpclassify

引数の浮動小数点の分類を返します。

## <a name="syntax"></a>構文

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

**fpclassify** は、引数 *x* の浮動小数点クラスを示す整数値を返します。 次の表は、で定義されている、 **fpclassify** によって返される値を示して \<math.h> います。

|値|説明|
|-----------|-----------------|
|**FP_NAN**|クワイエット型、シグナル型、または不確定の NaN|
|**FP_INFINITE**|正または負の無限大|
|**FP_NORMAL**|正規化された正または負の 0 以外の値|
|**FP_SUBNORMAL**|正規化されない正または負の値|
|**FP_ZERO**|正または負の 0 値|

## <a name="remarks"></a>解説

C では、 **fpclassify** はマクロです。C++ では、 **fpclassify** は **`float`** 、、 **`double`** 、またはの引数の型を使用してオーバーロードされた関数です **`long double`** 。 どちらの場合も、返される値は、中間表記ではなく、引数式の有効な型に依存します。 たとえば、法線 **`double`** または値は、 **`long double`** に変換するときに無限大、denormal、または0になることが **`float`** あります。

## <a name="requirements"></a>要件

|関数/マクロ|必須ヘッダー (C)|必須ヘッダー (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> または \<cmath>|

**Fpclassify** マクロおよび **fpclassify** 関数は、ISO C99 および c++ 11 仕様に準拠しています。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
