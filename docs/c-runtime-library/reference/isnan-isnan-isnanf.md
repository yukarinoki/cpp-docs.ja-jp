---
description: 詳細については、「isnan、_isnan、_isnanf」を参照してください。
title: isnan、_isnan、_isnanf
ms.date: 01/31/2019
api_name:
- _isnan
- _isnanf
- isnan
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
ms.openlocfilehash: 819b53740c6717f0ba8d18376a38c91c80ee03c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211246"
---
# <a name="isnan-_isnan-_isnanf"></a>isnan、_isnan、_isnanf

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

C では、引数 *x* が NAN の場合、 **isnan** マクロおよび **_isnan** および **_isnanf** 関数は0以外の値を返します。それ以外の場合は0を返します。

C++ では、 **isnan** テンプレート関数は、 **`true`** 引数 *x* が NaN の場合はを返し、それ以外の場合はを返し **`false`** ます。

## <a name="remarks"></a>解説

NaN 値は他の NaN 値と等しいとは比較されないため、これらの関数またはマクロのいずれかを使用して検出する必要があります。 浮動小数点演算の結果を、指定された型の IEEE-754 浮動小数点形式で表現できない場合、NaN が生成されます。 出力の NaN の表現方法については、「 [printf](printf-printf-l-wprintf-wprintf-l.md)」を参照してください。

C++ としてコンパイルされた場合、 **isnan** マクロは定義されず、代わりに **isnan** テンプレート関数が定義されます。 マクロと同じように動作しますが、整数ではなく型の値を返し **`bool`** ます。

**_Isnan** 関数と **_isnanf** 関数は、Microsoft 固有の関数です。 **_Isnanf** 関数は、x64 用にコンパイルされた場合にのみ使用できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**isnan**、 **_isnanf**|\<math.h>|\<math.h> または \<cmath>|
|**_isnan**|\<float.h>|\<float.h> または \<cfloat>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnormal](isnormal.md)<br/>
