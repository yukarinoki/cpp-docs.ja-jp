---
title: _stricoll、_wcsicoll、_mbsicoll、_stricoll_l、_wcsicoll_l、_mbsicoll_l
ms.date: 4/2/2020
api_name:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
- _o__mbsicoll
- _o__mbsicoll_l
- _o__stricoll
- _o__stricoll_l
- _o__wcsicoll
- _o__wcsicoll_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- stricoll
- _stricoll
- _wcsicoll
- mbsicoll_l
- _mbsicoll
- _ftcsicoll
- wcsicoll_l
- _tcsicoll
- mbsicoll
- stricoll_l
helpviewer_keywords:
- code pages, using for string comparisons
- _ftcsicoll function
- _mbsicoll_l function
- _mbsicoll function
- mbsicoll function
- stricoll function
- tcsicoll function
- string comparison [C++], culture-specific
- _tcsicoll function
- _stricoll function
- _stricoll_l function
- _wcsicoll function
- mbsicoll_l function
- stricoll_l function
- strings [C++], comparing by code page
- ftcsicoll function
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
ms.openlocfilehash: 9c023405043dea1c0a1d8e6d7f6fcc6505677583
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919989"
---
# <a name="_stricoll-_wcsicoll-_mbsicoll-_stricoll_l-_wcsicoll_l-_mbsicoll_l"></a>_stricoll、_wcsicoll、_mbsicoll、_stricoll_l、_wcsicoll_l、_mbsicoll_l

ロケール固有の情報を使用して文字列を比較します。

> [!IMPORTANT]
> **_mbsicoll**と **_mbsicoll_l**は、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _stricoll(
   const char *string1,
   const char *string2
);
int _wcsicoll(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicoll(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricoll_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicoll_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*string1*、 *string2*<br/>
Null で終わる比較対象の文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各関数は、次のように、 *string1*と*string2*の関係を示す値を返します。

|戻り値|string1 と string2 との関係|
|------------------|----------------------------------------|
|< 0|*string1*が*string2*未満|
|0|*string1*と*string2*の同一|
|> 0|*string1*が*string2*より大きい|
|**_NLSCMPERROR**|エラーが発生しました。|

これらの各関数は **_NLSCMPERROR**を返します。 **_NLSCMPERROR**を使用するには\<、string. h> \<または mbstring.h> を追加します。 *string1*または*string2*に照合シーケンスのドメイン外のワイド文字コードが含まれている場合、 **_wcsicoll**は失敗する可能性があります。 エラーが発生した場合、 **_wcsicoll**は**errno**を**EINVAL**に設定することがあります。 **_Wcsicoll**の呼び出し時にエラーが発生していないかどうかを確認するには、 **errno**を0に設定し、 **_wcsicoll**を呼び出した後に**errno**をチェックします。

## <a name="remarks"></a>解説

これらの各関数は、現在使用中のコードページに従って、 *string1*と*string2*の大文字と小文字を区別しない比較を実行します。 これらの関数は、現在のコード ページの文字セット順序と辞書式文字順序との間に相違点があり、この違いが文字列比較に関係がある場合にのみ使用します。

**_stricmp**は **_stricoll**とは異なります。 **_stricmp**の比較は**LC_CTYPE**の影響を受けますが、 **_stricoll**の比較は、ロケールの**LC_CTYPE**および**LC_COLLATE**のカテゴリに従っています。 **LC_COLLATE**カテゴリの詳細については、「 [setlocale](setlocale-wsetlocale.md)と[ロケールのカテゴリ](../../c-runtime-library/locale-categories.md)」を参照してください。 **_L**サフィックスが付いていないこれらの関数のバージョンは、現在のロケールを使用します。**_l**サフィックスが付いているバージョンは、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

これらのすべての関数では、パラメーターの検証が行われます。 *String1*または*string2*が**NULL**ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は **_NLSCMPERROR**を返し、 **errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicoll**|**_stricoll**|**_mbsicoll**|**_wcsicoll**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_stricoll**、 **_stricoll_l**|\<string.h>|
|**_wcsicoll**、 **_wcsicoll_l**|\<wchar.h>、\<string.h>|
|**_mbsicoll**、 **_mbsicoll_l**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[国](../../c-runtime-library/locale.md)<br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
