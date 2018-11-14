---
title: _create_locale、_wcreate_locale
ms.date: 11/04/2016
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 109a1d93692d0c65269b40fd0559381907ce1cab
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326564"
---
# <a name="createlocale-wcreatelocale"></a>_create_locale、_wcreate_locale

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

*category*<br/>
カテゴリ。

*locale*<br/>
ロケールの指定子。

## <a name="return-value"></a>戻り値

有効な場合*ロケール*と*カテゴリ*が与えられると、として指定されたロケールの設定を返します、 **_locale_t**オブジェクト。 プログラムの現在のロケール設定は変更されません。

## <a name="remarks"></a>Remarks

**_Create_locale**関数では、多くの CRT 関数のロケール固有のバージョンで使用するための特定のリージョン固有の設定を表すオブジェクトを作成することができます (関数、 **_l**サフィックス). 動作に似ています**setlocale**で現在の環境に、指定されたロケールの設定を適用するのではなく設定を保存する点を除いて、 **_locale_t**返される構造体。 **_Locale_t**を使用して構造体を解放する必要があります[_free_locale](free-locale.md)が不要になった場合。

**_wcreate_locale**のワイド文字バージョンです **_create_locale**、*ロケール*引数 **_wcreate_locale**はワイド文字列です。 **_wcreate_locale**と **_create_locale**動作は同じです。

*カテゴリ*引数は、影響を受けるロケール固有の動作の一部を指定します。 使用するフラグ*カテゴリ*影響されるプログラムの部分は次の表に示すようにします。

| *カテゴリ*フラグ | 影響が及ぶ対象 |
|-----------------|---------|
| **LC_ALL** |次に示すように、すべてのカテゴリです。 |
| **LC_COLLATE** |**Strcoll 系**、 **_stricoll**、 **wcscoll**、 **_wcsicoll**、 **strxfrm**、 **_strncoll**、 **_strnicoll**、 **_wcsncoll**、 **_wcsnicoll**、および**wcsxfrm**関数。 |
| **LC_CTYPE** | 文字処理関数 (を除く**isdigit**、 **isxdigit**、 **mbstowcs**、および**mbtowc**、影響を受けない)。 |
| **LC_MONETARY** | によって返される通貨の書式設定情報、 **localeconv**関数。 |
| **LC_NUMERIC** | 小数点文字の書式化出力ルーチン (など**printf**)、データ変換ルーチン、および非通貨の書式情報によって返される**localeconv**します。 小数点文字だけでなく**LC_NUMERIC**セット、数千の区切り記号と、グループ化の制御によって返される文字列[localeconv](localeconv.md)します。 |
| **LC_TIME** | **Strftime**と**wcsftime**関数。 |

この関数は、検証、*カテゴリ*と*ロケール*パラメーター。 カテゴリ パラメーターが、前の表で指定された値のいずれかでない場合、または場合*ロケール*は**NULL**、関数を返します**NULL**します。

*ロケール*引数は、ロケールを指定する文字列へのポインターです。 形式については、*ロケール*引数を参照してください[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)します。

*ロケール*引数には、ロケール名、言語の文字列を言語識別文字列と国/地域コード、コード ページでは、または、言語識別文字列、国/地域コード、およびコード ページを使用できます。 使用できるロケール名、言語、国/地域コード、およびコード ページのセットには、1 文字に 2 バイトを超えるデータを必要とする (UTF-7、UTF-8 など) コード ページを除き、Windows の NLS API でサポートされるすべてが含まれています。 Utf-7、utf-8 などのコード ページを提供する場合 **_create_locale**は失敗し、返す**NULL**します。 サポートされているロケール名のセット **_create_locale**されて[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)します。 サポートされている言語と国/地域の文字列のセット **_create_locale**は、「[言語識別文字列](../../c-runtime-library/language-strings.md)と[国/地域識別文字列](../../c-runtime-library/country-region-strings.md)します。

ロケール設定の詳細については、「[setlocale、_wsetlocale](setlocale-wsetlocale.md)」を参照してください。

この関数は、の以前の名前 **_ _create_locale** (2 つのアンダー スコア、使用は推奨されていません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[言語識別文字列](../../c-runtime-library/language-strings.md)<br/>
[Country/Region Strings](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
