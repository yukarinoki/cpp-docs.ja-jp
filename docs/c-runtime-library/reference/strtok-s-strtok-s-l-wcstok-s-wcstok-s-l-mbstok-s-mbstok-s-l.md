---
title: strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 467184acd7ef78ee52f1605d23f2d3b80e6adb83
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l

現在のロケールまたは渡されたロケールを使用して、文字列内の次のトークンを検索します。 これらのバージョンの [strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。

> [!IMPORTANT]
> **_mbstok_s**と **_mbstok_s_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

unsigned char* _mbstok_s(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
検索するトークンを含む文字列。

*delimiters*<br/>
使用する区切り記号文字のセット。

*context*<br/>
関数呼び出しの間の位置情報を格納するために使用します。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

見つかった次のトークンへのポインターを返します*str*です。 返します**NULL**以上トークンが見つかった場合。 各呼び出しを変更*str*返されたトークンの後に発生する最初の区切り文字の null 文字に置き換えることによってです。

### <a name="error-conditions"></a>エラー条件

|*str*|*delimiters*|*context*|戻り値|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**NULL**|任意|null ポインターへのポインター|**NULL**|**EINVAL**|
|任意|**NULL**|任意|**NULL**|**EINVAL**|
|任意|任意|**NULL**|**NULL**|**EINVAL**|

場合*str*は**NULL**が*コンテキスト*のポインターを有効なコンテキストのポインターでは、エラーはありません。

## <a name="remarks"></a>コメント

**Strtok_s**ファミリの関数の次のトークンを検索する*str*です。 一連の文字で*区切り記号*で検索するトークンの可能な区切り記号を指定*str*現在の呼び出しで。 **wcstok_s**と **_mbstok_s**のワイド文字とマルチバイト文字バージョンは、 **strtok_s**です。 引数と戻り値の**wcstok_s**と **_wcstok_s_l**ワイド文字は、文字列以外の **_mbstok_s**と **_mbstok_s_l**マルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。

この関数は、パラメーターを検証します。 表「エラー条件」に示すようなエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**返す**NULL**です。

最初の呼び出しで**strtok_s**関数は先行する区切り記号をスキップしの最初のトークンへのポインターを返します*str*、null 文字を含むトークンを終了します。 残りから複数のトークンを分けることができます*str*への呼び出しの系列で**strtok_s**です。 各呼び出し**strtok_s**変更*str*その呼び出しによって返されたトークンの後に null 文字を挿入することで。 *コンテキスト*ポインターの文字列が読み取られていると追跡、文字列で、次のトークンを読み取る。 次のトークンを読み取る*str*、呼び出す**strtok_s**で、 **NULL**値を*str*引数、同じを渡すと*コンテキスト*パラメーター。 **NULL** *str*引数により**strtok_s** 、変更後の次のトークンを検索する*str*です。 *区切り記号*引数取ることができる任意の値ごとに 1 回の呼び出しからように区切り記号のセットが異なる場合があります。

*コンテキスト*パラメーターで使用される静的バッファーよりも優先されます**strtok**と **_strtok_l**、同じスレッドで同時に 2 つの文字列を解析することができます。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 この関数のバージョン、 **_l**サフィックスは、このロケールに依存する動作に現在のスレッド ロケールを使用します。 バージョンで、 **_l**代わりに使用する点を除いて、サフィックスは同じ、*ロケール*パラメーター。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtok_s**|\<string.h>|
|**_strtok_s_l**|\<string.h>|
|**wcstok_s**、<br />**_wcstok_s_l**|\<string.h> または \<wchar.h>|
|**_mbstok_s**、<br />**_mbstok_s_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|\_UNICODE (& a) \_MBCS が定義されていません|\_MBCS の定義|_UNICODE が定義されている場合|
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
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
