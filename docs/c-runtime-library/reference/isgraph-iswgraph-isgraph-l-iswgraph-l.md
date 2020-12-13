---
description: '詳細については、次を参照してください: isgraph、iswgraph、_isgraph_l、_iswgraph_l'
title: isgraph、iswgraph、_isgraph_l、_iswgraph_l
ms.date: 4/2/2020
api_name:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
- _o_isgraph
- _o_iswgraph
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isgraph_l
- _iswgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
ms.openlocfilehash: 165972af4c921abb9026c6a3297426910cbf49e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332685"
---
# <a name="isgraph-iswgraph-_isgraph_l-_iswgraph_l"></a>isgraph、iswgraph、_isgraph_l、_iswgraph_l

整数がグラフィカルな文字を表すかどうかを判定します。

## <a name="syntax"></a>構文

```C
int isgraph(
   int c
);
int iswgraph(
   wint_t c
);
int _isgraph_l(
   int c,
   _locale_t locale
);
int _iswgraph_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

*C* がスペース以外の印刷可能な文字の特殊表現である場合、これらの各ルーチンは0以外の値を返します。 *c* がスペース以外の印刷可能な文字である場合、 **isgraph** は0以外の値を返します。 *c* がワイド文字のスペース以外の印刷可能なワイド文字である場合、 **iswgraph** は0以外の値を返します。 これらの各ルーチンは、 *c* がテスト条件を満たしていない場合は0を返します。

**_L** サフィックスを持つこれらの関数のバージョンでは、ロケールに依存する動作に現在のロケールではなく渡されたロケールが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*C* が EOF でない場合、または 0 ~ 0xff の範囲内にある場合、 **isgraph** と **_isgraph_l** の動作は未定義です。 デバッグ CRT ライブラリが使用され、 *c* がこれらの値のいずれでもない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraph**|**isgraph**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraph**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isgraph**|\<ctype.h>|
|**iswgraph**|\<ctype.h> または \<wchar.h>|
|**_isgraph_l**|\<ctype.h>|
|**_iswgraph_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
