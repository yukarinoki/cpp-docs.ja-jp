---
title: _stricoll、_wcsicoll、_mbsicoll、_stricoll_l、_wcsicoll_l、_mbsicoll_l
ms.date: 11/04/2016
apiname:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: bd2406751fd2855afd02743c98938e530398e7d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353665"
---
# <a name="stricoll-wcsicoll-mbsicoll-stricolll-wcsicolll-mbsicolll"></a>_stricoll、_wcsicoll、_mbsicoll、_stricoll_l、_wcsicoll_l、_mbsicoll_l

ロケール固有の情報を使用して文字列を比較します。

> [!IMPORTANT]
> **_mbsicoll**と **_mbsicoll_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

*string1*, *string2*<br/>
Null で終わる比較対象の文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの関数の関係を示す値を返します*string1*に*string2*、次のようにします。

|戻り値|string1 と string2 との関係|
|------------------|----------------------------------------|
|< 0|*string1*未満*string2*|
|0|*string1*と同じ*string2*|
|> 0|*string1*より大きい*string2*|
|**_NLSCMPERROR**|エラーが発生しました。|

これらの関数を返します。**すると**します。 使用する**すると**、いずれかを含める\<string.h > または\<mbstring.h >。 **_wcsicoll**場合に失敗できる*string1*または*string2*に照合シーケンスのドメイン外のワイド文字コードが含まれています。 エラーが発生したときに **_wcsicoll**設定**errno**に**EINVAL**します。 呼び出しでエラーをチェックする **_wcsicoll**設定**errno**を 0 にし、確認**errno**呼び出した後 **_wcsicoll**します。

## <a name="remarks"></a>Remarks

これらの各関数は、大文字と小文字を実行します。 *string1*と*string2*現在使用されているコード ページに従ってします。 これらの関数は、現在のコード ページの文字セット順序と辞書式文字順序との間に相違点があり、この違いが文字列比較に関係がある場合にのみ使用します。

**_stricmp**とは異なります **_stricoll**点で、 **_stricmp**比較が受ける**LC_CTYPE**であるのに対し、 **_stricoll**比較に基づいて、 **LC_CTYPE**と**LC_COLLATE**ロケールのカテゴリに分類します。 詳細については、 **LC_COLLATE**カテゴリを参照してください[setlocale](setlocale-wsetlocale.md)と[ロケールのカテゴリ](../../c-runtime-library/locale-categories.md)します。 この関数のバージョン、 **_l**サフィックスを使用しているバージョンは、現在のロケール、 **_l**代わりに渡されたロケールを使用する点を除いて、サフィックスは同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

これらのすべての関数では、パラメーターの検証が行われます。 いずれか*string1*または*string2*は**NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md). これらの関数を返すかどうかは、引き続き実行が許可された、**すると**設定と**errno**に**EINVAL**します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicoll**|**_stricoll**|**_mbsicoll**|**_wcsicoll**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_stricoll**、 **_stricoll_l**|\<string.h>|
|**_wcsicoll**、 **_wcsicoll_l**|\<wchar.h>、\<string.h>|
|**_mbsicoll**、 **_mbsicoll_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
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
