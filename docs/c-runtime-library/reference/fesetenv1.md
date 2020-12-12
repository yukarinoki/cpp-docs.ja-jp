---
description: '詳細情報: fesetenv'
title: fesetenv
ms.date: 04/05/2018
api_name:
- fesetenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 662634e467eb224af813f60ab4434d4857d21d50
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289440"
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

*ペン v*<br/>
[Fegetenv](fegetenv1.md)または [feholdexcept](feholdexcept2.md)の呼び出しによって設定された浮動小数点環境を含む **fenv_t** オブジェクトへのポインター。 **FE_DFL_ENV** マクロを使用して、既定のスタートアップ浮動小数点環境を指定することもできます。

## <a name="return-value"></a>戻り値

環境が正常に設定された場合は 0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>解説

Fesetenv 関数は、 が指すオブジェクト **fenv_t** に格納されている値から現在の浮動小数点環境 *を設定します。* 浮動小数点環境とは、浮動小数点計算に影響する一連の状態フラグと制御モードです。 浮動小数点例外の丸めモードと状態フラグが含まれます。  参照 *v* が **FE_DFL_ENV** ない場合、または有効な **fenv_t** オブジェクトを指していない場合、後続の動作は定義されません。

この関数を呼び出すと、 *このオブジェクトに* ある例外状態フラグが設定されますが、これらの例外は発生しません。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
