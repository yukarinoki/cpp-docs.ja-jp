---
title: nearbyint、nearbyintf、nearbyintl |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- nearbyint
- nearbyintf
- nerabyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2362a68bf73a370f2fdf8eaa5ecb18b0a08bfaad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint、nearbyintf、nearbyintl

指定の浮動小数点値を整数に丸め、浮動小数点形式でその値を返します。

## <a name="syntax"></a>構文

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
丸める値。

## <a name="return-value"></a>戻り値

成功した場合を返します*x*によって報告された、現在の丸めの形式を使用して、最も近い整数に丸められた、 [fegetround](fegetround-fesetround2.md)です。 それ以外の場合は、関数から次の値のいずれかが返されます。

|懸案事項|Return|
|-----------|------------|
|*x* ±INFINITY を =|±INFINITY、未変更の状態|
|*x* ±0 を =|±0、未変更の状態|
|*x* NaN を =|NaN|

エラーは報告されません[_matherr](matherr.md)。 具体的には、この関数はいずれかを報告できません**FE_INEXACT**例外。

## <a name="remarks"></a>コメント

この関数の主な違いと[rint](rint-rintf-rintl.md)は、この関数には、不正確な浮動小数点の例外は発生しません。

浮動小数点の最大値は正確な整数であるため、この関数が単独でオーバーフローすることはありません。むしろ、使用する関数のバージョンによっては、出力で戻り値がオーバーフローすることがあります。

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**nearbyint**を受け取り、返します**float**または**長い****二重**パラメーター。 C プログラムでは、 **nearbyint**常に 2 つの double 値を受け取って、double 値を返します。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**nearbyint**、 **nearbyintf**、 **nearbyintl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[数値演算と浮動小数点サポート](../floating-point-support.md)<br/>
