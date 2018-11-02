---
title: isnan、_isnan、_isnanf
ms.date: 04/05/2018
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
ms.openlocfilehash: ce111569b7caee9d0c7b8f35352c395571ad08b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650867"
---
# <a name="isnan-isnan-isnanf"></a>isnan、_isnan、_isnanf

浮動小数点値が非数 (NaN) かどうかをテストします。

## <a name="syntax"></a>構文

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

C では、 **isnan**マクロと **_isnan**と **_isnanf**関数が 0 以外の値を返す場合、引数*x* NAN は、それ以外の0 を返します。

C++ では、 **isnan**テンプレート関数を返します**true**場合引数*x* NAN; は、それ以外の場合を返す**false**。

## <a name="remarks"></a>Remarks

C **isnan**マクロと **_isnan**と **_isnanf**関数は浮動小数点値をテスト*x*、0 以外の値を返す場合*x*ない数 (NAN) 値。 NaN は、浮動小数点演算の結果が IEEE-754 浮動小数点形式の指定した型で表現できない場合に生成されます。 出力で NaN が表現される方法の詳細については、「[printf](printf-printf-l-wprintf-wprintf-l.md)」をご覧ください。

C++ としてコンパイルされるときに、 **isnan**マクロが定義されていないと**isnan**テンプレート関数は、代わりに定義されます。 型の値を返します**bool**整数ではなく。

**_Isnan**と **_isnanf**関数は、Microsoft 固有の仕様。 **_Isnanf**関数は、x64 用にコンパイルされるときに使用できるのみです。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**isnan**、 **_isnanf**|\<math.h>|\<math.h> または \<cmath>|
|**_isnan**|\<float.h>|\<float.h> または \<cfloat>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_finite、_finitef](finite-finitef.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
