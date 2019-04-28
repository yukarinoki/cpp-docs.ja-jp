---
title: logb、logbf、logbl、_logb、_logbf
ms.date: 04/05/2018
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
ms.openlocfilehash: 9f598eedaf30b1f2a1858129e648a117355d112e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285713"
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb、logbf、logbl、_logb、_logbf

浮動小数点引数の指数の値を抽出します。

## <a name="syntax"></a>構文

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**logb**の公平な指数値を返します*x*として、符号付き整数の浮動小数点値として表されます。

## <a name="remarks"></a>Remarks

**Logb**関数は、浮動小数点引数の指数値を抽出*x*場合と同様、 *x*無限範囲で表されていました。 場合、引数*x*は非正規化され、そのとして扱われます正規化されています。

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **logb**を受け取って返す**float**または**長い****二重**値。 C プログラムで**logb**は、**二重**します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|なし|_DOMAIN|
|± 0|ZERODIVIDE|_SING|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_logb**|\<float.h>|
|**logb**、 **logbf**、 **logbl**、 **_logbf**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
