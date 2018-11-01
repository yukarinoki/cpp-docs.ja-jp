---
title: fesetenv
ms.date: 04/05/2018
apiname:
- fesetenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 8c91bfbb89df964fed0a632d5fb5ebac47ebe948
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436150"
---
# <a name="fesetenv"></a>fesetenv

現在の浮動小数点環境を設定します。

## <a name="syntax"></a>構文

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>パラメーター

*penv*<br/>
ポインターを**fenv_t**への呼び出しで設定された浮動小数点環境を格納しているオブジェクト[fegetenv](fegetenv1.md)または[feholdexcept](feholdexcept2.md)します。 使用して、既定のスタートアップ浮動小数点環境を指定することも、 **FE_DFL_ENV**マクロ。

## <a name="return-value"></a>戻り値

環境が正常に設定された場合は 0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>Remarks

**Fesetenv**関数に格納されている値から現在の浮動小数点環境の設定、 **fenv_t**指すオブジェクト*penv*します。 浮動小数点環境とは、浮動小数点計算に影響する一連の状態フラグと制御モードです。 浮動小数点例外の丸めモードと状態フラグが含まれます。  場合*penv*は**FE_DFL_ENV**が有効なを指していないまたは**fenv_t**オブジェクト、その後の動作が定義されていません。

この関数の呼び出しが例外をされている状態フラグを設定、 *penv*オブジェクトがそれらの例外は発生しません。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
