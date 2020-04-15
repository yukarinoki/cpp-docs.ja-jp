---
title: iscntrl、iswcntrl、_iscntrl_l、_iswcntrl_l
ms.date: 4/2/2020
api_name:
- iscntrl
- _iswcntrl_l
- _iscntrl_l
- iswcntrl
- _o_iscntrl
- _o_iswcntrl
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _istcntrl_l
- _iswcntrl_l
- iswcntrl
- _iscntrl_l
- iscntrl
- _istcntrl
helpviewer_keywords:
- iscntrl function
- _iscntrl_l function
- _iswcntrl_l function
- _istcntrl function
- istcntrl function
- iswcntrl function
- _istcntrl_l function
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
ms.openlocfilehash: d3760102ca07c883ac711c66994ff470cb46cf84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343873"
---
# <a name="iscntrl-iswcntrl-_iscntrl_l-_iswcntrl_l"></a>iscntrl、iswcntrl、_iscntrl_l、_iswcntrl_l

整数が制御文字を表すかどうかを判定します。

## <a name="syntax"></a>構文

```C
int iscntrl(
   int c
);
int iswcntrl(
   wint_t c
);
int _iscntrl_l(
   int c,
   _locale_t locale
);
int _iswcntrl_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
テストする整数

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*c*が制御文字の特定の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 **iscntrl は***、c*が制御文字 (0x00 - 0x1F または 0x7F) の場合、ゼロ以外の値を戻します。 *c が*制御ワイド文字の場合 **、iswcntrl**はゼロ以外の値を戻します。 c がテスト条件を満た*さない場合*、これらのルーチンはそれぞれ 0 を返します。

**_l**サフィックスを持つこれらの関数のバージョンでは、現在のロケールの代わりに渡されるロケール パラメーターが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*c*が EOF でない場合、または 0 から 0xFF の範囲内である場合 **、iscntrl**および **_iscntrl_l**の動作は未定義です。 デバッグ CRT ライブラリが使用され *、c*がこれらの値の 1 つではない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istcntrl**|**iscntrl**|**iscntrl**|**イスフントル**|
|**_istcntrl_l**|**_iscntrl_l**|**_iscntrl_l**|**_iswcntrl_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**iscntrl**|\<ctype.h>|
|**イスフントル**|\<ctype.h> または \<wchar.h>|
|**_iscntrl_l**|\<ctype.h>|
|**_iswcntrl_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
