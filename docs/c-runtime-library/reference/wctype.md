---
description: '詳細情報: wctype'
title: wctype
ms.date: 1/14/2021
api_name:
- wctype
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.openlocfilehash: d0afd2bd163af967b11d0df58c84b62521ca6c2a
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242930"
---
# `wctype`

ワイド文字のコードの分類規則を決定します。

## <a name="syntax"></a>構文

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>パラメーター

*`property`*\
プロパティ文字列。

## <a name="return-value"></a>戻り値

**`LC_CTYPE`** 現在のロケールのカテゴリで、名前がプロパティ文字列に一致する分類規則が定義されていない場合 *`property`* 、この関数は0を返します。 それ以外の場合は、の後続の呼び出しに対する2番目の引数として使用するのに適した0以外の値を返し [`towctrans`](towctrans.md) ます。

## <a name="remarks"></a>注釈

この関数では、ワイド文字のコードの分類規則を決定します。 次の呼び出しのペアの動作はすべてのロケールで同じです (ただし、実装によって、"C" ロケールであっても追加の分類規則を定義できます)。

|関数|同等なもの|
|--------------|-------------|
|`iswalnum(c)`|`iswctype(c, wctype( "alnum" ))`|
|`iswalpha(c)`|`iswctype(c, wctype( "alpha" ))`|
|`iswcntrl(c)`|`iswctype(c, wctype( "cntrl" ))`|
|`iswdigit(c)`|`iswctype(c, wctype( "digit" ))`|
|`iswgraph(c)`|`iswctype(c, wctype( "graph" ))`|
|`iswlower(c)`|`iswctype(c, wctype( "lower" ))`|
|`iswprint(c)`|`iswctype(c, wctype( "print" ))`|
|`iswpunct(c)`|`iswctype(c, wctype( "punct" ))`|
|`iswspace(c)`|`iswctype(c, wctype( "space" ))`|
|`iswupper(c)`|`iswctype(c, wctype( "upper" ))`|
|`iswxdigit(c)`|`iswctype(c, wctype( "xdigit" ))`|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`wctype`|`<wctype.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>参照

[データ変換](../../c-runtime-library/data-conversion.md)\
[`setlocale`, `_wsetlocale`](setlocale-wsetlocale.md)
