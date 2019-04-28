---
title: fpclassify
ms.date: 04/05/2018
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: a25897a110d96923a45695d61f923dc7818c7e3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287942"
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

**fpclassify**引数の浮動小数点の分類を示す整数値を返します*x*します。 このテーブルは、によって返される値を示しています。 **fpclassify**で定義された\<math.h >。

|[値]|説明|
|-----------|-----------------|
|**FP_NAN**|クワイエット型、シグナル型、または不確定の NaN|
|**FP_INFINITE**|正または負の無限大|
|**FP_NORMAL**|正規化された正または負の 0 以外の値|
|**FP_SUBNORMAL**|正規化されない正または負の値|
|**FP_ZERO**|正または負の 0 値|

## <a name="remarks"></a>Remarks

C では、 **fpclassify**マクロは C++ では、 **fpclassify**の引数の型を使用するオーバー ロードされた関数は、 **float**、**二重**、または**長い** **二重**します。 どちらの場合も、返される値は、中間表記ではなく、引数式の有効な型に依存します。 たとえば、通常**二重**または**長い** **二重**値は、無限になる、denormal、またはゼロ値に変換すると、 **float**。

## <a name="requirements"></a>必要条件

|関数/マクロ|必須ヘッダー (C)|必須ヘッダー (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> または \<cmath>|

**Fpclassify**マクロと**fpclassify**関数は、ISO C99 および c++ 11 仕様に準拠しています。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
