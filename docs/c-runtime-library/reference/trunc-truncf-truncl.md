---
title: trunc、truncf、truncl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
dev_langs:
- C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67c179065a6b2c6fc10a4ba6ba87868c8306a2aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409460"
---
# <a name="trunc-truncf-truncl"></a>trunc、truncf、truncl

指定した浮動小数点以下に最も近い整数を指定します。

## <a name="syntax"></a>構文

```C
double trunc( double x );
float trunc( float x ); //C++ only
long double truncl( long double x );
```

```cpp
long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
切り捨てる値。

## <a name="return-value"></a>戻り値

成功した場合、整数値が返されます*x*0 方向に丸められた、します。

それ以外の場合は、次のいずれかを返します。

|懸案事項|Return|
|-----------|------------|
|*x* ±INFINITY を =|x|
|*x* ±0 を =|x|
|*x* NaN を =|NaN|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**trunc**を受け取り、返します**float**と**長い****二重**型です。 C プログラムでは、 **trunc**常に受け取りを返す、**二重**です。

浮動小数点の最大値はちょうど整数であるため、この関数は単独ではオーバーフローしません。 ただし、整数型に値を返すことによって、関数のオーバーフローが発生する場合があります。

浮動小数点から整数に暗黙的に変換することで切り捨てることもできますが、これは対象の型に格納できる値に限ります。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**trunc**、 **truncf**、 **truncl**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[floor、floorf、floorl](floor-floorf-floorl.md)<br/>
[ceil、ceilf、ceill](ceil-ceilf-ceill.md)<br/>
[round、roundf、roundl](round-roundf-roundl.md)<br/>
