---
title: setlocale、_wsetlocale
ms.date: 11/04/2016
apiname:
- _wsetlocale
- setlocale
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
ms.openlocfilehash: 618b3e58a52e89561439fe76bf1b30e3cbbce001
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356206"
---
# <a name="setlocale-wsetlocale"></a>setlocale、_wsetlocale

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

*category*<br/>
ロケールに影響されるカテゴリ。

*locale*<br/>
ロケールの指定子。

## <a name="return-value"></a>戻り値

有効な場合*ロケール*と*カテゴリ*は、指定した関連付けられた文字列ポインターを返します*ロケール*と*カテゴリ*します。 場合、*ロケール*または*カテゴリ*が正しくありません、null ポインターと、プログラムの現在のロケール設定は変更されませんを返します。

たとえば、

```C
setlocale( LC_ALL, "en-US" );
```

を呼び出すと、すべてのカテゴリを設定し、文字列だけを返します

```Output
en-US
```

によって返される文字列をコピーする**setlocale**プログラムのロケール情報の部分を復元します。 によって返される文字列のグローバルまたはスレッド ローカル ストレージが使用される**setlocale**します。 後で呼び出し**setlocale**前の呼び出しによって返される文字列のポインターを無効にすると、文字列を上書きします。

## <a name="remarks"></a>Remarks

使用して、 **setlocale**設定、変更、またはクエリで指定されたプログラムの現在のロケール情報の一部またはすべての関数*ロケール*と*カテゴリ*します。 *ロケール*プログラムの特定の側面をカスタマイズできますローカリティ (国/地域および言語) を参照します。 ロケールに依存するカテゴリとしては、日付の形式や通貨値の表示形式などがあります。 設定した場合*ロケール*をコンピューターにサポートされている複数の形式を持つ言語の既定の文字列を確認する必要があります、 **setlocale**に有効な言語の値を返します。 たとえば、設定した場合*ロケール*「簡体字中国語」または「繁体字中国語」を"chinese"戻り値になります。

**_wsetlocale**のワイド文字バージョンは、 **setlocale**、*ロケール*引数と戻り値 **_wsetlocale**はワイド文字列です。 **_wsetlocale**と**setlocale**動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

*カテゴリ*引数は、影響を受けるプログラムのロケール情報の一部を指定します。 使用するマクロ、*カテゴリ*影響されるプログラムの部分は、次のとおりと。

|*カテゴリ*フラグ|影響が及ぶ対象|
|-|-|
| **LC_ALL** | 次に示すように、すべてのカテゴリです。 |
| **LC_COLLATE** | **Strcoll 系**、 **_stricoll**、 **wcscoll**、 **_wcsicoll**、 **strxfrm**、 **_strncoll**、 **_strnicoll**、 **_wcsncoll**、 **_wcsnicoll**、および**wcsxfrm**関数。 |
| **LC_CTYPE** | 文字処理関数 (を除く**isdigit**、 **isxdigit**、 **mbstowcs**、および**mbtowc**、影響を受けない)。 |
| **LC_MONETARY** | によって返される通貨の書式設定情報、 **localeconv**関数。 |
| **LC_NUMERIC** | 小数点文字の書式化出力ルーチン (など**printf**)、データ変換ルーチン、および非通貨の書式情報によって返される**localeconv**します。 小数点文字だけでなく**LC_NUMERIC**セット、数千の区切り記号と、グループ化の制御によって返される文字列[localeconv](localeconv.md)します。 |
| **LC_TIME** | **Strftime**と**wcsftime**関数。 |

この関数は、カテゴリ パラメーターを検証します。 カテゴリ パラメーターが前の表に示されている値のいずれでもない場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は設定**errno**に**EINVAL**返します**NULL**します。

*ロケール*引数は、ロケールを指定する文字列へのポインターです。 形式については、*ロケール*引数を参照してください[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)します。 *ロケール*が空の文字列をポイントしている場合は、実装定義のネイティブ環境になります。 値**C** C 翻訳のための最小限の ANSI 規格環境を指定します。 **C**ロケールですべて**char**データ型は、1 バイト、およびそれらの値が 256 未満では常にします。

プログラムの開始時に、次のステートメントの等価性の確認が実行されます。

`setlocale( LC_ALL, "C" );`

*ロケール*引数には、ロケール名、言語の文字列を言語識別文字列と国/地域コード、コード ページでは、または、言語識別文字列、国/地域コード、およびコード ページを使用できます。 使用できるロケール名、言語、国/地域コード、およびコード ページのセットには、1 文字に 2 バイトを超えるデータを必要とする (UTF-7、UTF-8 など) コード ページを除き、Windows の NLS API でサポートされるすべてが含まれています。 Utf-7 または utf-8 のコード ページ値を指定した場合**setlocale**は失敗すると、返す**NULL**します。 サポートされているロケール名のセット**setlocale**されて[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)します。 サポートされている言語と国/地域の文字列のセット**setlocale**は、「[言語識別文字列](../../c-runtime-library/language-strings.md)と[国/地域識別文字列](../../c-runtime-library/country-region-strings.md)します。 パフォーマンス上の理由と、コードに埋め込まれた、またはストレージに対してシリアル化されたロケール文字列の保守容易性の理由により、ロケール名形式を使用することをお勧めします。 オペレーティング システムの更新によってロケール名の文字列が変更される可能性は、言語および国/地域名の形式よりも低くなっています。

として渡される null ポインター、*ロケール*引数**setlocale**国際的な環境を設定する代わりにクエリを実行します。 場合、*ロケール*引数が null ポインターで、プログラムの現在のロケール設定は変更されません。 代わりに、 **setlocale**に関連付けられている文字列へのポインターを返します、*カテゴリ*スレッドの現在のロケール。 場合、*カテゴリ*引数が**LC_ALL**セミコロンで区切られた、各カテゴリの現在の設定を示す文字列を返します。 たとえば、呼び出しのシーケンス 

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

の場合、

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

これは文字列に関連付けられている、 **LC_ALL**カテゴリ。

次の例に関連する、 **LC_ALL**カテゴリ。 文字列 ".OCP" および ".ACP" のどちらかをコード ページ番号の代わりに使用して、それぞれの文字列で、ユーザー既定の OEM コード ページおよびユーザー既定の ANSI コード ページを使用することを指定できます。

- `setlocale( LC_ALL, "" );`

   ロケールを既定に設定します。これはオペレーティング システムから取得したユーザー既定の ANSI コード ページです。

- `setlocale( LC_ALL, ".OCP" );`

   ロケールに、オペレーティング システムから取得した現在の OEM コード ページを明示的に設定します。

- `setlocale( LC_ALL, ".ACP" );`

   ロケールに、オペレーティング システムから取得した ANSI コード ページを設定します。

- `setlocale( LC_ALL, "<localename>" );`

   ロケールに、*\<localename>* で表されるロケール名を設定します。

- `setlocale( LC_ALL, "<language>_<country>" );`

   ロケールに、*\<language>* と *\<country>* で表される言語と国/地域、およびホスト オペレーティング システムから取得した既定のコード ページを設定します。

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   によって示される言語、国/地域、およびコード ページに、ロケールの設定、 *\<言語 >*、 *\<国 >*、および *\<code_page>* 文字列。 言語、国/地域、およびコード ページはさまざまに組み合わせて使用できます。 たとえば、次の呼び出しは、ロケールに、カナダ フランス語、およびコード ページ 1252 を設定します。

   `setlocale( LC_ALL, "French_Canada.1252" );`

   次の呼び出しは、ロケールに、カナダ フランス語、および既定の ANSI コード ページを設定します。

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   次の呼び出しは、ロケールに、カナダ フランス語、および既定の OEM コード ページを設定します。

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   ロケールに *\<language>* で表される言語を設定し、指定した言語の既定の国/地域と、その国/地域のユーザー既定の ANSI コード ページをホスト オペレーティング システムから取得して使用します。 たとえば、次の呼び出しを**setlocale**は機能的に同等です。

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   パフォーマンスと保守性の理由から、最初の形式を使用することをお勧めします。

- `setlocale( LC_ALL, ".<code_page>" );`

   コード ページに、*<code_page>* で表される値、および指定したコード ページの既定の国/地域と言語 (ホスト オペレーティング システムによって定義) を設定します。

カテゴリはいずれかである必要があります**LC_ALL**または**LC_CTYPE**を変更するコード ページ。 たとえば場合は、既定の国/地域と、ホスト オペレーティング システムの言語は、"United States"と「英語」には、次の 2 つを呼び出す**setlocale**は機能的に同等です。

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

詳細については、「[C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)」の [setlocale](../../preprocessor/setlocale.md) pragma ディレクティブをご覧ください。

関数は、 [_configthreadlocale](configthreadlocale.md)かどうか制御するために使用が**setlocale**プログラム内のすべてのスレッドのロケールまたは呼び出し元のスレッドのロケールだけに影響を与えます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
