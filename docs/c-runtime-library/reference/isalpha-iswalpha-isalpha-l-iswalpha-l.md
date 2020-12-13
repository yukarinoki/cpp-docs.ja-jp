---
description: '詳細については、次を参照してください: isalpha、iswalpha、_isalpha_l、_iswalpha_l'
title: isalpha、iswalpha、_isalpha_l、_iswalpha_l
ms.date: 4/2/2020
api_name:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
- _o_isalpha
- _o_iswalpha
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
- _istalpha
- _ismbcalpha_l
- isalpha
- _isalpha_l
- iswalpha
- _istalpha_l
- _iswalpha_l
helpviewer_keywords:
- _iswalpha_l function
- _isalpha_l function
- _ismbcalpha_l function
- _istalpha_l function
- _ismbcalpha function
- isalpha function
- iswalpha function
- istalpha function
- _istalpha function
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
ms.openlocfilehash: 044564d64c9f7d358633a866c53a25e6ab16d26a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332762"
---
# <a name="isalpha-iswalpha-_isalpha_l-_iswalpha_l"></a>isalpha、iswalpha、_isalpha_l、_iswalpha_l

整数が英字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isalpha(
   int c
);
int iswalpha(
   wint_t c
);
int _isalpha_l(
   int c,
   _locale_t locale
);
int _iswalpha_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

*locale*<br/>
現在のロケールの代わりに使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンは、 *c* が英文字の特殊表現である場合は0以外の値を返します。 *c* が a ~ z または a ~ z の範囲内にある場合、 **isalpha** は0以外の値を返します。 **iswalpha** は、 [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) または **iswlower** が0以外のワイド文字に対してのみ0以外の値を返します。つまり、 **iswcntrl**、 **iswdigit**、 **iswpunct**、または **iswspace** のいずれも0以外に設定されている実装定義セットの1つであるワイド文字の場合です。 これらの各ルーチンは、 *c* がテスト条件を満たしていない場合は0を返します。

**_L** サフィックスを持つこれらの関数のバージョンでは、現在のロケールの代わりに渡されたロケールパラメーターを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*C* が EOF でない場合、または 0 ~ 0xff の範囲内にある場合、 **isalpha** と **_isalpha_l** の動作は未定義です。 デバッグ CRT ライブラリが使用され、 *c* がこれらの値のいずれでもない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isalpha**|\<ctype.h>|
|**iswalpha**|\<ctype.h> または \<wchar.h>|
|**_isalpha_l**|\<ctype.h>|
|**_iswalpha_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
