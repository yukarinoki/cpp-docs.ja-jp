---
title: setlocale, _wsetlocale
description: Microsoft C ランタイム (CRT) ライブラリsetlocale関数_wsetlocaleと .
ms.date: 4/2/2020
api_name:
- _wsetlocale
- setlocale
- _o__wsetlocale
- _o_setlocale
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
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
no-loc:
- setlocale
- _wsetlocale
ms.openlocfilehash: 2834229839153c3154caadf71e5fb30d84ed2f1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353720"
---
# <a name="setlocale-_wsetlocale"></a>setlocale、_wsetlocale

実行時ロケールを設定または取得します。

## <a name="syntax"></a>構文

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>パラメーター

*カテゴリ*\
ロケールに影響されるカテゴリ。

*ロケール*\
ロケールの指定子。

## <a name="return-value"></a>戻り値

有効な*ロケール*と*カテゴリ*が指定されている場合は、指定した*ロケール*と*カテゴリ*に関連付けられた文字列へのポインタを返します。 *ロケール*または*カテゴリ*が有効でない場合は、null ポインターを返し、プログラムの現在のロケール設定は変更されません。

たとえば、

```C
setlocale( LC_ALL, "en-US" );
```

を呼び出すと、すべてのカテゴリを設定し、文字列だけを返します

```Output
en-US
```

**setlocale**によって返された文字列をコピーして、プログラムのロケール情報のその部分を復元することができます。 setlocale によって返される文字列には、グローバルまたはスレッド**setlocale**ローカルストレージが使用されます。 setlocale**setlocale**の後の呼び出しは、以前の呼び出しによって返された文字列ポインタを無効にする文字列を上書きします。

## <a name="remarks"></a>解説

**setlocale**関数を使用して、 *locale*および*category*で指定された現在のプログラムロケール情報の一部または全部を設定、変更、または照会します。 *locale*は、プログラムの特定の側面をカスタマイズできる地域 (国/地域および言語) を指します。 ロケールに依存するカテゴリとしては、日付の形式や通貨値の表示形式などがあります。 コンピュータでサポートされている複数のフォームを持つ言語の*ロケール*を既定の文字列に設定する場合は **、setlocale**の戻り値を調べて、どの言語が有効になっているかを確認する必要があります。 たとえば、*ロケール*を "中国語" に設定すると、戻り値は "簡体字中国語" または "繁体字中国語" になります。

**_wsetlocale**は**setlocale**のワイド文字バージョンです。_wsetlocaleの*ロケール*引数と戻り**値はワイド**文字列です。 **_wsetlocale**と**setlocale**は、それ以外の場合と同様に動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**Setlocale**|**Setlocale**|**_wsetlocale**|

*category*引数は、影響を受けるプログラムのロケール情報の部分を指定します。 *カテゴリ*およびそれらが影響を与えるプログラムの部分に使用されるマクロは次のとおりです。

|*カテゴリ*フラグ|影響|
|-|-|
| **Lc_all** | 次に示すように、すべてのカテゴリです。 |
| **LC_COLLATE** | **strcoll**、 **_stricoll**、 **wcscoll**、 **_wcsicoll**、 **strxfrm**、 **_strncoll**、 _strnicoll 、 **_wcsncoll**、 **_wcsnicoll**、 および**wcsxfrm**関数。 **_wcsncoll** |
| **LC_CTYPE** | 文字処理関数 **(isdigit** **、isxdigit** **、mbstowcs**、**および mbtowc**を除く) |
| **LC_MONETARY** | **localeconv**関数によって返される通貨フォーマット情報。 |
| **LC_NUMERIC** | フォーマット済み出力ルーチン **(printf**など) の小数点文字 (データ変換ルーチン、および**localeconv**によって返される非金銭的なフォーマット情報)。 小数点文字に加えて **、LC_NUMERIC**は、桁区切り記号と[localeconv](localeconv.md)によって返されるグループ化制御文字列を設定します。 |
| **LC_TIME** | **strftime**関数と**wcsftime**関数。 |

この関数は、カテゴリ パラメーターを検証します。 category パラメーターが前の表に示された値の 1 つでない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は**errno**を**EINVAL**に設定し **、NULL**を返します。

*ロケール*引数は、ロケールを指定する文字列へのポインターです。 *ロケール*引数の形式については、「[ロケール名、言語、および国/地域の文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」を参照してください。 *ロケール*が空の文字列をポイントしている場合は、実装定義のネイティブ環境になります。 値 C は **、C**変換の最小 ANSI 準拠環境を指定します。 **C**ロケールでは、すべての**char**データ型が 1 バイトであり、その値が常に 256 未満であると想定しています。

プログラムの開始時に、次のステートメントの等価性の確認が実行されます。

`setlocale( LC_ALL, "C" );`

*locale*引数には、ロケール名、言語文字列、言語文字列と国/地域コード、コード ページ、または言語文字列、国/地域コード、およびコード ページを使用できます。 利用可能なロケール名、言語、国/地域コード、およびコード ページには、Windows NLS API でサポートされているすべてのロケール名が含まれています。 **setlocale**でサポートされるロケール名のセットについては、「[ロケール名、言語、および国/地域文字列」を参照してください](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)。 **setlocale**でサポートされる言語および国/地域の文字列のセットは、[言語文字列](../../c-runtime-library/language-strings.md)と[国/地域文字列](../../c-runtime-library/country-region-strings.md)に一覧表示されます。 パフォーマンス上の理由と、コードに埋め込まれた、またはストレージに対してシリアル化されたロケール文字列の保守容易性の理由により、ロケール名形式を使用することをお勧めします。 オペレーティング システムの更新によってロケール名の文字列が変更される可能性は、言語および国/地域名の形式よりも低くなっています。

*ロケール*引数として渡される null ポインターは、国際環境を設定するのではなく **、setlocale**に照会を指示します。 *ロケール*引数が null ポインターの場合、プログラムの現在のロケール設定は変更されません。 代わりに **、setlocale**は、スレッドの現在のロケールの*カテゴリ*に関連付けられている文字列へのポインターを返します。 *category*引数が**LC_ALL**場合、関数は、各カテゴリの現在の設定をセミコロンで区切って示す文字列を返します。 たとえば、呼び出しのシーケンス 

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

は、次の値は返します。

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

LC_ALL**カテゴリに**関連付けられている文字列です。

次の例は **、LC_ALL**カテゴリに関連しています。 文字列のどちらか".OCP"と"。ACP" は、コード ページ番号の代わりに、ユーザー既定の OEM コード ページと、そのロケール名に対するユーザー既定の ANSI コード ページの使用を指定するために使用できます。

- `setlocale( LC_ALL, "" );`

   ロケールを既定に設定します。これはオペレーティング システムから取得したユーザー既定の ANSI コード ページです。 ロケール名は[、GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)によって返される値に設定されます。 コード ページは[GetACP](/windows/win32/api/winnls/nf-winnls-getacp)によって返される値に設定されます。

- `setlocale( LC_ALL, ".OCP" );`

   オペレーティング システムから取得した現在の OEM コード ページにロケールを設定します。 ロケール名は[、GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)によって返される値に設定されます。 コード ページは[、GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によって、ユーザーの既定のロケール名の[LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, ".ACP" );`

   ロケールに、オペレーティング システムから取得した ANSI コード ページを設定します。 ロケール名は[、GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)によって返される値に設定されます。 コード ページは[、GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によって、ユーザー既定のロケール名の[LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, "<localename>" );`

   ロケール名が>で示される*\<ロケール名に設定*します。 コード ページは[、GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によって指定されたロケール名の[LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, "<language>_<country>" );`

   言語*\<>* および*\<国>* で示される言語と国/地域に、ホスト オペレーティング システムから取得した既定のコード ページをロケールに設定します。 コード ページは[、GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によって指定されたロケール名の[LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   言語、国/地域、および*\<言語>*、*\<国>、* および*\<code_page>* 文字列で示されるコード ページにロケールを設定します。 言語、国/地域、およびコード ページはさまざまに組み合わせて使用できます。 たとえば、次の呼び出しは、ロケールに、カナダ フランス語、およびコード ページ 1252 を設定します。

   `setlocale( LC_ALL, "French_Canada.1252" );`

   次の呼び出しは、ロケールに、カナダ フランス語、および既定の ANSI コード ページを設定します。

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   次の呼び出しは、ロケールに、カナダ フランス語、および既定の OEM コード ページを設定します。

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   *\<ロケールを言語>* で示される言語に設定し、指定した言語の既定の国/地域を使用し、ホスト オペレーティング システムから取得したその国/地域の既定の ANSI コード ページを使用します。 たとえば **、setlocale**の次の呼び出しは機能的に同等です。

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   パフォーマンスと保守性の理由から、最初の形式を使用することをお勧めします。

- `setlocale( LC_ALL, ".<code_page>" );`

   コード ページに、*<code_page>* で表される値、および指定したコード ページの既定の国/地域と言語 (ホスト オペレーティング システムによって定義) を設定します。

コード ページの変更を有効にするには、カテゴリを**LC_ALL**または**LC_CTYPE**にする必要があります。 たとえば、ホスト オペレーティング システムの既定の国/地域と言語が "米国" と "英語" の場合 **、setlocale**の次の 2 つの呼び出しは機能的に同等です。

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

詳細については、「[C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)」の [setlocale](../../preprocessor/setlocale.md) pragma ディレクティブをご覧ください。

setlocale[_configthreadlocale](configthreadlocale.md)がプログラム内のすべてのスレッド**setlocale**のロケールに影響するか、または呼び出し元スレッドのロケールのみに影響するかを制御するために、_configthreadlocale関数を使用します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>関連項目

[ロケール名、言語、国/地域の文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)\
[ロケール](../../c-runtime-library/locale.md)\
[ロケールコンフ](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[ストレン、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[ムストフツ、_mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[_mbtowc_l、mbtowc](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[関数](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb、_wctomb_l](wctomb-wctomb-l.md)
