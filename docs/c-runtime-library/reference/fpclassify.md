---
title: fpclassify | Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.topic: reference
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da55cb87804d178d5a305ed466aa498de4bc1ee5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398433"
---
# <a name="fpclassify"></a>fpclassify

引数の浮動小数点の分類を返します。

## <a name="syntax"></a>構文

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only

```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

**fpclassify**を浮動小数点引数のクラスを示す整数値を返します*x*です。 次の表は、によって返される値を示します**fpclassify**で定義されている\<math.h >。

|[値]|説明|
|-----------|-----------------|
|**FP_NAN**|クワイエット型、シグナル型、または不確定の NaN|
|**FP_INFINITE**|正または負の無限大|
|**FP_NORMAL**|正規化された正または負の 0 以外の値|
|**FP_SUBNORMAL**|正規化されない正または負の値|
|**FP_ZERO**|正または負の 0 値|

## <a name="remarks"></a>コメント

C では、 **fpclassify**マクロです C++ では、 **fpclassify**の引数の型を使用するオーバー ロードされた関数は、 **float**、**二重**、または。**長い****二重**です。 どちらの場合も、返される値は、中間表記ではなく、引数式の有効な型に依存します。 たとえば、通常**二重**または**長い****二重**値は、無限になる、denormal、または 0 の値に変換すると、 **float**です。

## <a name="requirements"></a>要件

|関数/マクロ|必須ヘッダー (C)|必須ヘッダー (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> または \<cmath>|

**Fpclassify**マクロと**fpclassify**関数は、ISO C99 と c++ 11 仕様に準拠しています。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
