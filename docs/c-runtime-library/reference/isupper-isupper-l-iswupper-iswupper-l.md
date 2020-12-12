---
description: '詳細については、次を参照してください: isupper、_isupper_l、iswupper、_iswupper_l'
title: isupper、_isupper_l、iswupper、_iswupper_l
ms.date: 4/2/2020
api_name:
- isupper
- iswupper
- _iswupper_l
- _isupper_l
- _o_isupper
- _o_iswupper
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- isupper
- _istupper
- iswupper
helpviewer_keywords:
- istupper function
- iswupper function
- isupper_l function
- _isupper_l function
- iswupper_l function
- _istupper function
- _iswupper_l function
- isupper function
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
ms.openlocfilehash: d9af298cd1577473cac0db1ab6eda0be895d0c1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289141"
---
# <a name="isupper-_isupper_l-iswupper-_iswupper_l"></a>isupper、_isupper_l、iswupper、_iswupper_l

整数が大文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isupper(
   int c
);
int _isupper_l (
   int c,
   _locale_t locale
);
int iswupper(
   wint_t c
);
int _iwsupper_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンは、 *c* が特殊文字の特殊表現である場合は0以外の値を返します。 *c* が大文字 (a-z) の場合、 **isupper** は0以外の値を返します。 **iswupper** は、 *c* が大文字に対応するワイド文字である場合、または *c* が、 **iswcntrl**、 **iswdigit**、 **iswpunct**、または **iswspace** のいずれも0以外のワイド文字の実装定義セットの1つである場合、0以外の値を返します。 これらの各ルーチンは、 *c* がテスト条件を満たしていない場合は0を返します。

**_L** サフィックスを持つこれらの関数のバージョンでは、ロケールに依存する動作に現在のロケールではなく渡されたロケールが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*C* が EOF でない場合、または 0 ~ 0xff の範囲内にある場合、 **isupper** と **_isupper_l** の動作は未定義です。 デバッグ CRT ライブラリが使用され、 *c* がこれらの値のいずれでもない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istupper**|**isupper**|[_ismbcupper](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**iswupper**|
|**_istupper_l**|**_isupper_l**|[_ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_iswupper_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isupper**|\<ctype.h>|
|**_isupper_l**|\<ctype.h>|
|**iswupper**|\<ctype.h> または \<wchar.h>|
|**_iswupper_l**|\<ctype.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
