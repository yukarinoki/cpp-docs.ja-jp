---
title: isnan、_isnan、_isnanf | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baf92397087ebbac27c7fea8cf5f524b33736b19
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401153"
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

C では、 **isnan**マクロと **_isnan**と **_isnanf**場合、関数は 0 以外の値を返す引数*x* nan ですそれ以外の場合、。0 を返します。

C++ では、 **isnan**テンプレート関数を返します**true**場合引数*x* nan です。 それ以外の場合を返します**false**。

## <a name="remarks"></a>コメント

C **isnan**マクロと **_isnan**と **_isnanf**関数は浮動小数点値をテスト*x*場合は、0 以外の値を返す*x*ない数 (NAN) 値です。 NaN は、浮動小数点演算の結果が IEEE-754 浮動小数点形式の指定した型で表現できない場合に生成されます。 出力で NaN が表現される方法の詳細については、「[printf](printf-printf-l-wprintf-wprintf-l.md)」をご覧ください。

C++ としてコンパイルするとき、 **isnan**マクロが定義されていないと、 **isnan**テンプレート関数が代わりに定義されています。 型の値を返します**bool**整数ではなくです。

**_Isnan**と **_isnanf**関数は、Microsoft 固有の仕様です。 **_Isnanf**関数は、x64 用にコンパイルされたときに使用できるのみです。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**isnan**、 **_isnanf**|\<math.h>|\<math.h> または \<cmath>|
|**_isnan**|\<float.h>|\<float.h> または \<cfloat>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_finite、_finitef](finite-finitef.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
