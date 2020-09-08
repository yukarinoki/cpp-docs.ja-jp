---
title: copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl
description: 1つの引数の絶対値と、copysign () を使用した別の引数の符号を持つ値を返す API 参照
ms.date: 9/1/2020
api_name:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
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
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
ms.openlocfilehash: 8f9ffe56e82f6a82da15fde3f8efea60fc1c0f9f
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554865"
---
# <a name="copysign-copysignf-copysignl-_copysign-_copysignf-_copysignl"></a>copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl

ある引数の絶対値と別の引数の符号を持つ値を返します。

## <a name="syntax"></a>構文

```C
double copysign(
   double x,
   double y
);
float copysign(
   float x,
   float y
); // C++ only
long double copysign(
   long double x,
   long double y
); // C++ only
float copysignf(
   float x,
   float y
); // C++ only
long double copysignl(
   long double x,
   long double y
); // C++ only
double _copysign(
   double x,
   double y
);
long double _copysignl(
   long double x,
   long double y
);
#define copysign(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
結果の絶対値として返される浮動小数点値。

*前年*\
結果の符号として返される浮動小数点値。

[浮動小数点サポート ルーチン](../../c-runtime-library/floating-point-support.md)

## <a name="return-value"></a>戻り値

**Copysign**関数は、 *x*の大きさと*y*の符号を組み合わせた浮動小数点値を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す **copysign** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **copysign** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `copysign()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_copysign**|\<float.h>|
|**copysign**、 **copysignf**、 **copysignl**、 **_copysignf**、 **_copysignl**|\<math.h>|
|**copysign** マクロ | \<tgmath.h> |

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
[_chgsign、_chgsignf、_chgsignl](chgsign-chgsignf-chgsignl.md)<br/>
