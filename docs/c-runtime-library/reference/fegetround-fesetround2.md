---
description: 詳細については、「fegetround、fesetround」を参照してください。
title: fegetround、fesetround
ms.date: 04/05/2018
api_name:
- fegetround
- fesetround
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
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
ms.openlocfilehash: f3c112efc1c380ac4ce4495f4365e2a47a1d8fd2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322551"
---
# <a name="fegetround-fesetround"></a>fegetround、fesetround

現在の浮動小数点丸めモードを取得または設定します。

## <a name="syntax"></a>構文

```C
int fegetround(void);

int fesetround(
   int round_mode
);
```

### <a name="parameters"></a>パラメーター

*round_mode*<br/>
浮動小数点丸めマクロの 1 つとして設定する丸めモード。 値が浮動小数点丸めマクロのどれとも等しくない場合は、丸めモードは変更されません。

## <a name="return-value"></a>戻り値

成功した場合、 **fegetround** は、浮動小数点丸めマクロ値の1つとして丸めモードを返します。 現在の丸めモードを決定できない場合は、負の値を返します。

成功した場合、 **fesetround** は0を返します。 それ以外の場合、0 以外の値が返されます。

## <a name="remarks"></a>解説

浮動小数点演算には、いくつかある丸めモードのいずれかを使用できます。 これらは、結果が格納されるときに、浮動小数点演算の結果がどちらの方向に丸められるかを制御します。 次に、で定義されている浮動小数点丸めマクロの名前と動作を示し \<fenv.h> ます。

|マクロ|説明|
|-----------|-----------------|
|FE_DOWNWARD|負の無限大方向に丸めます。|
|FE_TONEAREST|最近似値に丸めます。|
|FE_TOWARDZERO|0 方向に丸めます。|
|FE_UPWARD|正の無限大方向に丸めます。|

FE_TONEAREST の既定の動作は、表現値の中間で偶数の (0) 最下位ビットを持つ最近似値に丸めます。

現在の丸めモードは、これらの操作に影響します:

- 文字列変換。

- 定数式の外部での浮動小数点算術演算子の結果。

- **Rint** や **nearbyint** などのライブラリ丸め関数。

- 標準ライブラリの数学関数から値を返します。

現在の丸めモードは、これらの操作に影響しません:

- **Trunc**、 **ceil**、 **floor**、および **lround** ライブラリ関数。

- 常に 0 方向に丸める、浮動小数点数から整数への暗黙的なキャストと変換。

- 常に最近似値に丸める、定数式での浮動小数点算術演算子の結果。

これらの関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fegetround**、 **fesetround**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[nearbyint、nearbyintf、nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint、rintf、rintl](rint-rintf-rintl.md)<br/>
[lrint、lrintf、lrintl、llrint、llrintf、llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
