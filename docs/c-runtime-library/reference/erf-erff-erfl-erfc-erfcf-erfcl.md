---
title: erf、erff、erfl、erfc、erfcf、erfcl
ms.date: 11/19/2018
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: 5c64a7ac6c3a4d79c221ff1ca5f9460e9e6bdea6
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176824"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf、erff、erfl、erfc、erfcf、erfcl

値の誤差関数または相補誤差関数を計算します。

## <a name="syntax"></a>構文

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**Erf**関数は、ガウスの誤差関数を返します*x*します。 **Erfc**関数返すガウスの相補誤差関数の*x*します。

## <a name="remarks"></a>Remarks

**Erf**関数のガウスの誤差関数を計算する*x*、として定義されています。

![X の誤差関数](media/crt_erf_formula.PNG "x の誤差関数")

1 - として補完的なガウスの誤差関数が定義されている erf(x) します。 **Erf**関数は、1.0 の場合は-1.0 の範囲の値を返します。 エラーの戻り値はありません。 **Erfc**関数は、0 ~ 2 の範囲の値を返します。 場合*x*に対して大きすぎる**erfc**、 **errno**に変数が設定されている**ERANGE**します。

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **erf**と**erfc**を受け取って返す**float**と**長い** **二重**型。 C プログラムで**erf**と**erfc**は、**二重**します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**erf**、 **erff**、 **erfl**、 **erfc**、 **erfcf**、 **erfcl**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
