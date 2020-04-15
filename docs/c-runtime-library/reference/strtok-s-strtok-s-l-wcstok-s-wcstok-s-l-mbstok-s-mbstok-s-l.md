---
title: strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l
ms.date: 4/2/2020
api_name:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
- _o__mbstok_s
- _o__mbstok_s_l
- _o_strtok_s
- _o_wcstok_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
ms.openlocfilehash: 9fe89fb897a5459b16c49060359b4bb40bc062a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365214"
---
# <a name="strtok_s-_strtok_s_l-wcstok_s-_wcstok_s_l-_mbstok_s-_mbstok_s_l"></a>strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l

現在のロケールまたは渡されたロケールを使用して、文字列内の次のトークンを検索します。 これらのバージョンの [strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。

> [!IMPORTANT]
> **_mbstok_s**と **_mbstok_s_l**は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char* strtok_s(
   char* str,
   const char* delimiters,
   char** context
);

char* _strtok_s_l(
   char* str,
   const char* delimiters,
   char** context,
   _locale_t locale
);

wchar_t* wcstok_s(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context
);

wchar_t *_wcstok_s_l(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context,
   _locale_t locale
);

unsigned char* _mbstok_s(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context
);

unsigned char* _mbstok_s_l(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
検索するトークンを含む文字列。

*delimiters*<br/>
使用する区切り文字のセット。

*context*<br/>
関数の呼び出し間に位置情報を格納するために使用します。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*str*で見つかった次のトークンへのポインターを返します。 トークンが見つからない場合は**NULL を**返します。 各呼び出しは、返されたトークンの後に最初に発生する区切り文字に null 文字を代入して*str*を変更します。

### <a name="error-conditions"></a>エラー条件

|*Str*|*delimiters*|*context*|戻り値|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**NULL**|any|null ポインターへのポインター|**NULL**|**Einval**|
|any|**NULL**|any|**NULL**|**Einval**|
|any|any|**NULL**|**NULL**|**Einval**|

*str*が**NULL**で *、コンテキスト*が有効なコンテキスト ポインターへのポインターである場合、エラーはありません。

## <a name="remarks"></a>解説

**関数のstrtok_s**ファミリは*str*で次のトークンを検索します。 *区切り文字*の中の文字のセットは、現在の呼び出しの*str*で見つかるトークンの可能な区切り文字を指定します。 **wcstok_s**と **_mbstok_s**は、ワイド文字とマルチバイト文字のstrtok_sのバージョン**です**。 **wcstok_s**と **_wcstok_s_l**の引数と戻り値はワイド文字列です。**_mbstok_s**および **_mbstok_s_l**の文字列は、マルチバイト文字文字列です。 それ以外では、これらの関数の動作は同じです。

この関数は、パラメーターを検証します。 エラー条件テーブルのようにエラー条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメータ ハンドラが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し **、NULL**を返します。

**strtok_s**の最初の呼び出しでは、関数は先頭の区切り文字をスキップし *、str*内の最初のトークンへのポインターを返し、null 文字でトークンを終了します。 **strtok_s**への一連の呼び出しによって *、str*の残りの部分からさらに多くのトークンを分割できます。 **strtok_s**呼び出しのたびに、その呼び出しによって返されるトークンの後に null 文字を挿入することによって*str*が変更されます。 *コンテキスト*ポインターは、読み取られる文字列と、文字列内の次のトークンが読み取られる場所を追跡します。 *str*から次のトークンを読み取る場合は *、str*引数に**null 値**を指定して**strtok_s**を呼び出し、同じ*コンテキスト*パラメーターを渡します。 **NULL** *str*引数を指定すると **、strtok_s変更**された*str*内の次のトークンが検索されます。 *区切り文字*の引数は、区切り文字のセットが異なる可能性があるため、1 つの呼び出しから次の呼び出しまで任意の値を取ることができます。

*context*パラメーターは**strtok**および **_strtok_l**で使用される静的バッファーに優先するため、同じスレッドで 2 つの文字列を同時に解析できます。

出力値は、ロケールの**LC_CTYPE**カテゴリ設定の設定によって影響されます。 詳細については、「[setlocale](setlocale-wsetlocale.md)」をご覧ください。

**_l**サフィックスを持たないこれらの関数のバージョンでは、このロケールに依存する動作に現在のスレッド ロケールが使用されます。 **_l**サフィックスを持つバージョンは *、locale*パラメーターで指定されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtok_s**|\<string.h>|
|**_strtok_s_l**|\<string.h>|
|**wcstok_s**、<br />**_wcstok_s_l**|\<string.h> または \<wchar.h>|
|**_mbstok_s**、<br />**_mbstok_s_l**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|\_ユニコード\_& MBCS が定義されていません|\_定義された MBCS|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok_s**|**strtok_s**|**_mbstok_s**|**wcstok_s**|
|**_tcstok_s_l**|**_strtok_s_l**|**_mbstok_s_l**|**_wcstok_s_l**|

## <a name="example"></a>例

```C
// crt_strtok_s.c
// In this program, a loop uses strtok_s
// to print all the tokens (separated by commas
// or blanks) in two strings at the same time.

#include <string.h>
#include <stdio.h>

char string1[] =
    "A string\tof ,,tokens\nand some  more tokens";
char string2[] =
    "Another string\n\tparsed at the same time.";
char seps[]   = " ,\t\n";
char *token1 = NULL;
char *token2 = NULL;
char *next_token1 = NULL;
char *next_token2 = NULL;

int main(void)
{
    printf("Tokens:\n");

    // Establish string and get the first token:
    token1 = strtok_s(string1, seps, &next_token1);
    token2 = strtok_s(string2, seps, &next_token2);

    // While there are tokens in "string1" or "string2"
    while ((token1 != NULL) || (token2 != NULL))
    {
        // Get next token:
        if (token1 != NULL)
        {
            printf(" %s\n", token1);
            token1 = strtok_s(NULL, seps, &next_token1);
        }
        if (token2 != NULL)
        {
            printf("        %s\n", token2);
            token2 = strtok_s(NULL, seps, &next_token2);
        }
    }
}
```

```Output
Tokens:
A
        Another
string
        string
of
        parsed
tokens
        at
and
        the
some
        same
more
        time.
tokens
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
