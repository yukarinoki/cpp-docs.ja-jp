---
title: wctype
ms.date: 11/04/2016
apiname:
- wctype
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
apitype: DLLExport
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 81caf8e1ab04635d205d7b01af2d4c2896eec01c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456902"
---
# <a name="wctype"></a>wctype

ワイド文字のコードの分類規則を決定します。

## <a name="syntax"></a>構文

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>パラメーター

*プロパティ*<br/>
プロパティ文字列。

## <a name="return-value"></a>戻り値

場合、 **LC_CTYPE**の現在のロケールのカテゴリがプロパティ文字列が名前に一致する分類規則を定義していない*プロパティ*関数は 0 を返します。 それ以外の場合、[towctrans](towctrans.md) への後続の呼び出しに対する 2 番目の引数として使用するのに適した 0 以外の値を返します。

## <a name="remarks"></a>Remarks

この関数では、ワイド文字のコードの分類規則を決定します。 次の呼び出しのペアの動作はすべてのロケールで同じです (ただし、実装によって、"C" ロケールであっても追加の分類規則を定義できます)。

|関数|同等なもの|
|--------------|-------------|
|iswalnum(c)|iswctype (c、wctype ("alnum"))|
|iswalpha(c)|iswctype (c、wctype (「アルファ」))|
|iswcntrl(c)|iswctype (c、wctype ("cntrl"))|
|iswdigit(c)|iswctype (c、wctype (「桁」))|
|iswgraph(c)|iswctype (c、wctype (「グラフ」))|
|iswlower(c)|iswctype (c、wctype (「低」))|
|iswprint(c)|iswctype (c、wctype ("print"))|
|iswpunct(c)|iswctype (c、wctype ("punct"))|
|iswspace(c)|iswctype (c、wctype (「容量」))|
|iswupper(c)|iswctype (c、wctype ("upper"))|
|iswxdigit(c)|iswctype (c、wctype ("xdigit"))|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
