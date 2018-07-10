---
title: strchr、wcschr、_mbschr、_mbschr_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strchr
- wcschr
- _mbschr_l
- _mbschr
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _ftcschr
- strchr
- wcschr
- _tcschr
- _mbschr
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- mbschr function
- _ftcschr function
- _mbschr function
- characters [C++], finding in strings
- _mbschr_l function
- ftcschr function
- wcschr function
- strchr function
- _tcschr function
- tcschr function
- mbschr_l function
ms.assetid: 2639905d-e983-43b7-b885-abef32cfac43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d83407efee1da2bc1c59cf0d869f54f6022a4eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415530"
---
# <a name="strchr-wcschr-mbschr-mbschrl"></a>strchr、wcschr、_mbschr、_mbschr_l
現在のロケールまたは指定された LC_CTYPE 変換状態カテゴリを使用し、文字列内の文字を探します。

> [!IMPORTANT]
> **_mbschr**と **_mbschr_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *strchr(
   const char *str,
   int c
);  // C only
char *strchr(
   char * str,
   int c
); // C++ only
const char *strchr(
   const char * str,
   int c
); // C++ only
wchar_t *wcschr(
   const wchar_t *str,
   wchar_t c
); // C only
wchar_t *wcschr(
   wchar_t *str,
   wchar_t c
);  // C++ only
const wchar_t *wcschr(
   const wchar_t *str,
   wchar_t c
);  // C++ only
unsigned char *_mbschr(
   const unsigned char *str,
   unsigned int c
); // C only
unsigned char *_mbschr(
   unsigned char *str,
   unsigned int c
); // C++ only
const unsigned char *_mbschr(
   const unsigned char *str,
   unsigned int c
); // C++ only
unsigned char *_mbschr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C only
unsigned char *_mbschr_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
const unsigned char *_mbschr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*str*<br/>
NULL で終わる元の文字列。

*c*<br/>
検索する文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの関数ポインターを返しますの最初に出現する*c*で*str*、または**NULL**場合*c*が見つかりません。

## <a name="remarks"></a>コメント

**Strchr**関数は、最初に見つかった位置を検索*c*で*str*、またはを返します**NULL**場合*c*は見つかりませんでした。 検索対象には終端の null 文字が含まれます。

**wcschr**、 **_mbschr**と **_mbschr_l**のワイド文字とマルチバイト文字バージョンは、 **strchr**です。 引数と戻り値の**wcschr**ワイド文字は、文字列以外の **_mbschr**マルチバイト文字列です。 **_mbschr**マルチバイト文字のシーケンスを認識します。 また、文字列が null ポインターである場合、 **_mbschr** 」の説明に従って、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合 **_mbschr**返します**NULL**設定と**errno**に**EINVAL**です。 **strchr**と**wcschr**はそのパラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

出力値の設定の影響を受けた、 **LC_CTYPE**カテゴリ; 詳細については、ロケールの設定、表示[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C では、これらの関数が受け取る、* * const * *、最初の引数のポインター。 C++ では、2 つのオーバーロードを使用できます。 ポインターを受け取るオーバー ロード * * const * * へのポインターを返します**const **; へのポインターを受け取る非**const * * へのポインターを返しますではない**const**です。マクロ **_CRT_CONST_CORRECT_OVERLOADS**場合は、両方が定義されている、 **const * * と非-** const * * これらの関数のバージョンを利用できます。必要な以外の場合**const * * 両方の C++ オーバー ロードの動作のシンボルを定義する **_CONST_RETURN**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcschr**|**strchr**|**_mbschr**|**wcschr**|
|**_n/a**|**該当なし**|**_mbschr_l**|**該当なし**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strchr**|\<string.h>|
|**wcschr**|\<string.h> または \<wchar.h>|
|**_mbschr**、 **_mbschr_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strchr.c
//
// This program illustrates searching for a character
// with strchr (search forward) or strrchr (search backward).
//

#include <string.h>
#include <stdio.h>

int  ch = 'r';

char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int result;

   printf_s( "String to be searched:\n      %s\n", string );
   printf_s( "      %s\n      %s\n\n", fmt1, fmt2 );
   printf_s( "Search char:   %c\n", ch );

   // Search forward.
   pdest = strchr( string, ch );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf_s( "Result:   first %c found at position %d\n",
              ch, result );
   else
      printf_s( "Result:   %c not found\n", ch );

   // Search backward.
   pdest = strrchr( string, ch );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf_s( "Result:   last %c found at position %d\n", ch, result );
   else
      printf_s( "Result:\t%c not found\n", ch );
}
```

```Output
String to be searched:
      The quick brown dog jumps over the lazy fox
               1         2         3         4         5
      12345678901234567890123456789012345678901234567890

Search char:   r
Result:   first r found at position 12
Result:   last r found at position 30
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strstr、wcsstr、_mbsstr、_mbsstr_l](strstr-wcsstr-mbsstr-mbsstr-l.md)<br/>
