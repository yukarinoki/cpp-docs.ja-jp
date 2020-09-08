---
title: cos、cosf、cosl
description: Cos、cosf、cosf の API リファレンス浮動小数点数のコサイン値を計算する。
ms.date: 08/31/2020
api_name:
- cos
- cosf
- cosl
- _o_cos
- _o_cosf
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- cos
- cosf
- cosl
helpviewer_keywords:
- cosines
- cosl function
- calculating cosine
- cosf function
- cos function
- trigonometric functions
- cosines, calculating
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
ms.openlocfilehash: b0e723708076067cf4d2ed896542ac08406a87ee
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556802"
---
# <a name="cos-cosf-cosl"></a>cos、cosf、cosl

コサインを計算します。

## <a name="syntax"></a>構文

```C
double cos( double x );
float cosf( float x );
long double cosl( long double x );
#define cos(X) // Requires C11 or higher

float cos( float x );  // C++ only
long double cos( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

*X*のコサイン。 *X*が263以上、または-263 以下の場合は、結果の有意性が失われます。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|なし|**_DOMAIN**|
|± INF|**無効です**|**_DOMAIN**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す **cos** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **cos** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `cos()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**cos**、 **cosh**、 **cosf**|\<math.h>|\<cmath> または \<math.h>|
|**cos ()** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[Sin、sinf、sinf](sin-sinf-sinl.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[asin、asinf、asinl](asin-asinf-asinl.md)<br/>
[atan、atanf、atanl、atan2、atan2f、atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[_matherr](matherr.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[tan、tanf、tanl](tan-tanf-tanl.md)<br/>
[_CIcos](../../c-runtime-library/cicos.md)<br/>
