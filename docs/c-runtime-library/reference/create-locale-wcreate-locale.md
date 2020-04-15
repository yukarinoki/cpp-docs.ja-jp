---
title: _create_locale、_wcreate_locale
ms.date: 4/2/2020
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
- _o__create_locale
- _o__wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- create_locale
- _create_locale
- __create_locale
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
ms.openlocfilehash: 611eaf342776b9a0f57c4f55c52a841c3fd13fb5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348253"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale、_wcreate_locale

ロケール オブジェクトを作成します。

## <a name="syntax"></a>構文

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>パラメーター

*カテゴリ*<br/>
カテゴリ。

*ロケール*<br/>
ロケールの指定子。

## <a name="return-value"></a>戻り値

有効な*ロケール*と*カテゴリ*が指定されている場合、指定されたロケール設定を **_locale_t**オブジェクトとして返します。 プログラムの現在のロケール設定は変更されません。

## <a name="remarks"></a>解説

**_create_locale**関数を使用すると、多くの CRT 関数 **(_l**サフィックスを持つ関数) のロケール固有のバージョンで使用するために、特定の地域固有の設定を表すオブジェクトを作成できます。 この動作は**setlocale**に似ていますが、指定したロケール設定を現在の環境に適用する代わりに、設定が返される **_locale_t**構造に保存されます。 **_locale_t**構造は、不要になった[時点で_free_locale](free-locale.md)を使用して解放する必要があります。

**_wcreate_locale**はワイド文字の **_create_locale**です。**_wcreate_locale**する*ロケール*引数はワイド文字ストリングです。 **_wcreate_locale**と **_create_locale**は同じように動作します。

*category*引数は、影響を受けるロケール固有の動作の部分を指定します。 *カテゴリ*に使用されるフラグと、それらが影響を与えるプログラムの部分は、次の表に示されています。

| *カテゴリ*フラグ | 影響 |
|-----------------|---------|
| **Lc_all** |次に示すように、すべてのカテゴリです。 |
| **LC_COLLATE** |**strcoll**、 **_stricoll**、 **wcscoll**、 **_wcsicoll**、 **strxfrm**、 **_strncoll**、 _strnicoll 、 **_wcsncoll**、 **_wcsnicoll**、 および**wcsxfrm**関数。 **_wcsncoll** |
| **LC_CTYPE** | 文字処理関数 **(isdigit** **、isxdigit** **、mbstowcs**、**および mbtowc**を除く) |
| **LC_MONETARY** | **localeconv**関数によって返される通貨フォーマット情報。 |
| **LC_NUMERIC** | フォーマット済み出力ルーチン **(printf**など) の小数点文字 (データ変換ルーチン、および**localeconv**によって返される非金銭的なフォーマット情報)。 小数点文字に加えて **、LC_NUMERIC**は、桁区切り記号と[localeconv](localeconv.md)によって返されるグループ化制御文字列を設定します。 |
| **LC_TIME** | **strftime**関数と**wcsftime**関数。 |

この関数は、*カテゴリ*と*ロケール*のパラメーターを検証します。 カテゴリ パラメータが前の表で指定された値の 1 つでない場合、または*locale*が**NULL**の場合、関数は**NULL**を返します。

*ロケール*引数は、ロケールを指定する文字列へのポインターです。 *ロケール*引数の形式については、「[ロケール名、言語、および国/地域の文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」を参照してください。

*locale*引数には、ロケール名、言語文字列、言語文字列と国/地域コード、コード ページ、または言語文字列、国/地域コード、およびコード ページを使用できます。 利用可能なロケール名、言語、国/地域コード、およびコード ページには、Windows NLS API でサポートされるすべてが含まれます。 **_create_locale**でサポートされるロケール名のセットについては、「[ロケール名、言語、および国/地域文字列」を参照してください](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)。 **_create_locale**でサポートされる言語および国/地域の文字列のセットは、[言語文字列](../../c-runtime-library/language-strings.md)と[国/地域文字列](../../c-runtime-library/country-region-strings.md)に一覧表示されます。

ロケール設定の詳細については、「[setlocale、_wsetlocale](setlocale-wsetlocale.md)」を参照してください。

この関数の以前の名前**である__create_locale** (2 つの先頭にアンダースコアが付いています) は非推奨になりました。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>関連項目

[ロケール名、言語、国/地域の文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../../c-runtime-library/language-strings.md)<br/>
[国/地域別文字列](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[Setlocale](../../preprocessor/setlocale.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
