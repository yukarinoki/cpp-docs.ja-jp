---
title: setlocale, _wsetlocale
description: Microsoft C runtime (CRT) ライブラリ関数とについて説明し setlocale _wsetlocale ます。
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 812aab43667416a5892d8e24d03d0e67cad8d0ac
ms.sourcegitcommit: b51703a96ee35ee2376d5f0775b70f03ccbe6d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88086995"
---
# <a name="no-locsetlocale-no-loc_wsetlocale"></a>setlocale, _wsetlocale

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

*別*\
ロケールに影響されるカテゴリ。

*locale*\
ロケールの指定子。

## <a name="return-value"></a>戻り値

有効な*ロケール*と*カテゴリ*が指定されている場合、は、指定された*ロケール*および*カテゴリ*に関連付けられている文字列へのポインターを返します。 *ロケール*または*カテゴリ*が有効でない場合、は null ポインターを返し、プログラムの現在のロケール設定は変更されません。

たとえば、

```C
setlocale( LC_ALL, "en-US" );
```

を呼び出すと、すべてのカテゴリを設定し、文字列だけを返します

```Output
en-US
```

`setlocale` によって返された文字列をコピーして、プログラムのロケール情報のその部分を復元できます。 `setlocale` によって返された文字列に対しては、グローバルまたはスレッド ローカル ストレージが使用されます。 その後 `setlocale` を呼び出すと文字列が上書きされ、前の呼び出しで返された文字列のポインターは無効になります。

## <a name="remarks"></a>解説

関数を使用し `setlocale` て、 *locale*および*category*によって指定された現在のプログラムのロケール情報の一部またはすべてを設定、変更、または照会します。 *ロケール*とは、プログラムの特定の側面をカスタマイズできる地域 (国/地域と言語) を指します。 ロケールに依存するカテゴリとしては、日付の形式や通貨値の表示形式などがあります。 コンピューターで複数の形式がサポートされている言語の既定の文字列に*ロケール*を設定した場合は、戻り値をチェックして、有効な言語を確認する必要があり `setlocale` ます。 たとえば、 *locale*を "中国語" に設定した場合、戻り値は "簡体字中国語または繁体字中国語" のいずれかになります。

`_wsetlocale`は、のワイド文字バージョンです `setlocale` 。の*ロケール*引数と戻り値 `_wsetlocale` はワイド文字列です。 それ以外では、`_wsetlocale` と `setlocale` の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|

*Category*引数は、影響を受けるプログラムのロケール情報の部分を指定します。 *Category*に使用されるマクロと、影響を与えるプログラムの部分は次のとおりです。

|*カテゴリ*フラグ|影響|
|-|-|
| `LC_ALL` | 次に示すように、すべてのカテゴリです。 |
| `LC_COLLATE` | `strcoll`、`_stricoll`、`wcscoll`、`_wcsicoll`、`strxfrm`、`_strncoll`、`_strnicoll`、`_wcsncoll`、`_wcsnicoll`、および `wcsxfrm` の各関数。 |
| `LC_CTYPE` | 文字処理関数の (影響を受けない `isdigit`、`isxdigit`、`mbstowcs`、および `mbtowc` を除く)。 |
| `LC_MONETARY` | `localeconv` 関数が返す通貨形式情報。 |
| `LC_NUMERIC` | `printf` などの書式化出力ルーチン、データ変換ルーチン、および `localeconv` が返す通貨形式以外の形式情報で使用される小数点文字。 小数点文字に加え、`LC_NUMERIC` は桁区切り記号、および [localeconv](localeconv.md) によって返されるグループ化コントロールの文字列を設定します。 |
| `LC_TIME` | `strftime` および `wcsftime` 関数。 |

この関数は、カテゴリ パラメーターを検証します。 Category パラメーターが前の表に示した値のいずれでもない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`NULL` を返します。

*Locale*引数は、ロケールを指定する文字列へのポインターです。 *Locale*引数の形式の詳細については、「[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」を参照してください。 *ロケール*が空の文字列をポイントしている場合は、実装定義のネイティブ環境になります。 `C` の値は、C 翻訳のための ANSI に準拠した最小環境を指定します。 `C` ロケールは、すべての ``char`` データ型が 1 バイトであり、それらの値は常に 256 未満であると推定します。

プログラムの開始時に、次のステートメントの等価性の確認が実行されます。

`setlocale( LC_ALL, "C" );`

*Locale*引数は、ロケール名、言語文字列、言語文字列と国/地域コード、コードページ、言語文字列、国/地域コード、およびコードページを受け取ることができます。 使用できるロケール名、言語、国/地域コード、およびコードページのセットには、Windows NLS API でサポートされているものがすべて含まれています。 `setlocale` でサポートされているロケール名のセットについては、「[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」に記載されています。 `setlocale` でサポートされる言語識別文字列と国/地域識別文字列は、「[言語識別文字列](../../c-runtime-library/language-strings.md)」および「[国/地域識別文字列](../../c-runtime-library/country-region-strings.md)」に記載されています。 パフォーマンス上の理由と、コードに埋め込まれた、またはストレージに対してシリアル化されたロケール文字列の保守容易性の理由により、ロケール名形式を使用することをお勧めします。 オペレーティング システムの更新によってロケール名の文字列が変更される可能性は、言語および国/地域名の形式よりも低くなっています。

*Locale*引数として渡される null ポインターは、 `setlocale` 国際環境を設定するのではなく、クエリを実行するように指示します。 *Locale*引数が null ポインターの場合、プログラムの現在のロケール設定は変更されません。 代わりに、は、 `setlocale` スレッドの現在のロケールの*カテゴリ*に関連付けられている文字列へのポインターを返します。 *Category*引数がの場合 `LC_ALL` 、関数は、各カテゴリの現在の設定をセミコロンで区切って示す文字列を返します。 たとえば、呼び出しのシーケンス 

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

は、`LC_ALL` カテゴリに対応する文字列です。

次の例は `LC_ALL` のカテゴリに関連するものです。 文字列 "のいずれかです。OCP "and"。コードページ番号の代わりに、ACP "を使用して、ユーザーの既定の OEM コードページとユーザー既定の ANSI コードページの使用をそれぞれ指定することができます。

- `setlocale( LC_ALL, "" );`

   ロケールを既定に設定します。これはオペレーティング システムから取得したユーザー既定の ANSI コード ページです。 ロケール名は、 [Getuserdefaultlocalename](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)によって返される値に設定されます。 コードページは、 [Getacp](/windows/win32/api/winnls/nf-winnls-getacp)によって返される値に設定されます。

- `setlocale( LC_ALL, ".OCP" );`

   ロケールを、オペレーティングシステムから取得した現在の OEM コードページに設定します。 ロケール名は、 [Getuserdefaultlocalename](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)によって返される値に設定されます。 コードページは、 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によってユーザーの既定のロケール名の[LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, ".ACP" );`

   ロケールに、オペレーティング システムから取得した ANSI コード ページを設定します。 ロケール名は、 [Getuserdefaultlocalename](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)によって返される値に設定されます。 コードページは、 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によってユーザーの既定のロケール名の[LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, "<localename>" );`

   ロケールをによって示されるロケール名に設定 *\<localename>* します。 コードページは、 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によって指定されたロケール名の[LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, "<language>_<country>" );`

   ロケールを、 *\<language>* *\<country>* ホストオペレーティングシステムから取得した既定のコードページと共に、およびによって示される言語と国/地域に設定します。 コードページは、 [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)によって指定されたロケール名の[LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants)値に設定されます。

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   ロケールを、、、およびの各文字列で示される言語、国/地域、およびコードページに設定し *\<language>* *\<country>* *\<code_page>* ます。 言語、国/地域、およびコード ページはさまざまに組み合わせて使用できます。 たとえば、次の呼び出しは、ロケールに、カナダ フランス語、およびコード ページ 1252 を設定します。

   `setlocale( LC_ALL, "French_Canada.1252" );`

   次の呼び出しは、ロケールに、カナダ フランス語、および既定の ANSI コード ページを設定します。

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   次の呼び出しは、ロケールに、カナダ フランス語、および既定の OEM コード ページを設定します。

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   ロケールをによって示される言語に設定 *\<language>* し、ホストオペレーティングシステムから取得した、指定した言語の既定の国/地域と、その国/地域のユーザー既定の ANSI コードページを使用します。 たとえば、次の `setlocale` の呼び出しは同等です。

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   パフォーマンスと保守性の理由から、最初の形式を使用することをお勧めします。

- `setlocale( LC_ALL, ".<code_page>" );`

   コード ページに、*<code_page>* で表される値、および指定したコード ページの既定の国/地域と言語 (ホスト オペレーティング システムによって定義) を設定します。

カテゴリは、コード ページの変更に影響する `LC_ALL` または `LC_CTYPE` である必要があります。 たとえば、ホスト オペレーティング システムの既定の国/地域と言語が "United States" と "English" の場合、次の `setlocale` の 2 種類の呼び出しは機能的に同じです。

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

詳細については、「 [setlocale](../../preprocessor/setlocale.md) [C/c + + プリプロセッサリファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)」のプラグマディレクティブを参照してください。

`setlocale` がプログラムのすべてのスレッドのロケールに影響するか、または呼び出しスレッドのロケールだけに影響するかを制御するには、関数 [_configthreadlocale](configthreadlocale.md) を使用します。

## <a name="utf-8-support"></a>UTF-8 のサポート

Windows 10 ビルド 17134 (4 月2018更新プログラム) 以降では、ユニバーサル C ランタイムは UTF-8 コードページの使用をサポートしています。 これは、 `char` C ランタイム関数に渡される文字列では、utf-8 エンコーディングで文字列が想定されることを意味します。 UTF-8 モードを有効にするには、を使用するときにコードページとして "UTF-8" を使用し `setlocale` ます。 たとえば、 `setlocale(LC_ALL, ".utf8")` は、現在の既定の WINDOWS ANSI コードページ (ACP) をロケールに、utf-8 をコードページに使用します。

を呼び出す `setlocale(LC_ALL, ".UTF8")` と、" 😊 " がに渡され、 `mbtowcs` 文字列に適切に変換され `wchar_t` ます。これに対して、以前はロケールの設定は使用できませんでした。

UTF-8 モードは `char` 、既定の WINDOWS ANSI コードページ (ACP) を使用して、以前に翻訳された文字列を含む関数に対しても有効です。 たとえば、 [`_mkdir("😊")`](../reference/mkdir-wmkdir.md) utf-8 コードページを使用してを呼び出すと、プログラムを実行する前に ACP を utf-8 に変更する必要がなく、フォルダー名としてその絵文字を持つディレクトリが正しく生成されます。 同様に、 [`_getcwd()`](../reference/getcwd-wgetcwd.md) そのフォルダー内でを呼び出すと、utf-8 でエンコードされた文字列が返されます。 互換性のために、C ロケールのコードページが UTF-8 に設定されていない場合でも、ACP は引き続き使用されます。

UTF-8 を使用できない C ランタイムの次の側面は、プログラムの起動中に設定されており、既定の Windows ANSI コードページ (ACP) を使用する必要があるためです。 [`__argv`](../argc-argv-wargv.md) [`_acmdln`](../acmdln-tcmdln-wcmdln.md) [`_pgmptr`](../pgmptr-wpgmptr.md)

以前のバージョンでは、、、 [ `c16rtomb` 、 `c32rtomb` および](../reference/c16rtomb-c32rtomb1.md) [ `mbrtoc16` `mbrtoc32` は、utf-8](../reference/mbrtoc16-mbrtoc323.md)のナロー文字列、utf-16 (Windows プラットフォームと同じエンコード)、 `wchar_t` および 32 utf-8 を変換するために存在していました。 互換性上の理由から、これらの Api は、によって設定されたコードページではなく、UTF-8 との間でのみ変換を行い `setlocale` ます。

Windows 7 などの Windows 10 より前の OS でこの機能を使用するには、[アプリローカル展開](../../windows/universal-crt-deployment.md#local-deployment)を使用するか、Windows SDK 以降のバージョン17134を使用して静的にリンクする必要があります。 17134より前の Windows 10 オペレーティングシステムでは、静的リンクのみがサポートされています。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`setlocale`|\<locale.h>|
|`_wsetlocale`|\<locale.h> または \<wchar.h>|

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

[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)\
[国](../../c-runtime-library/locale.md)\
[localeconv](localeconv.md)\
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)\
[strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)\
[strftime、wcsftime、_strftime_l、_wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb、_wctomb_l](wctomb-wctomb-l.md)
