---
title: strstr、wcsstr、_mbsstr、_mbsstr_l
ms.date: 4/2/2020
api_name:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
- _o__mbsstr
- _o__mbsstr_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
ms.openlocfilehash: 1fb6c025ec324fceb1b11dd23ed61500f08b4535
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911000"
---
# <a name="strstr-wcsstr-_mbsstr-_mbsstr_l"></a>strstr、wcsstr、_mbsstr、_mbsstr_l

文字列で最初に見つかった検索文字列へのポインターを返します。

> [!IMPORTANT]
> `_mbsstr` および `_mbsstr_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *strstr(
   const char *str,
   const char *strSearch
); // C only
char *strstr(
   char *str,
   const char *strSearch
); // C++ only
const char *strstr(
   const char *str,
   const char *strSearch
); // C++ only
wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C only
wchar_t *wcsstr(
   wchar_t *str,
   const wchar_t *strSearch
); // C++ only
const wchar_t *wcsstr(
   const wchar_t *str,
   const wchar_t *strSearch
); // C++ only
unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C only
unsigned char *_mbsstr(
   unsigned char *str,
   const unsigned char *strSearch
); // C++ only
const unsigned char *_mbsstr(
   const unsigned char *str,
   const unsigned char *strSearch
); // C++ only
unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C only
unsigned char *_mbsstr_l(
   unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
const unsigned char *_mbsstr_l(
   const unsigned char *str,
   const unsigned char *strSearch,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*引数*<br/>
NULL で終わる検索対象の文字列。

*strSearch*<br/>
NULL で終わる検索する文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*Str*で*strsearch*が最初に出現する位置へのポインター、または*strsearch*が*STR*に出現しない場合は NULL を返します。 *Strsearch*が長さ0の文字列を指している場合、関数は*str*を返します。

## <a name="remarks"></a>解説

関数`strstr`は、 *str*で最初に出現する*strsearch*へのポインターを返します。 検索には、終端の NULL 文字は含まれません。 `wcsstr` は `strstr` のワイド文字バージョンであり、`_mbsstr` はマルチバイト文字バージョンです。 `wcsstr` 関数の引数と戻り値はワイド文字列で、`_mbsstr` 関数の引数と戻り値はマルチバイト文字列です。 `_mbsstr` はそのパラメーターを検証します。 *Str*または*STRSEARCH*が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可され`_mbsstr`た`errno`場合、は EINVAL に設定し、0を返します。 `strstr` および `wcsstr` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの問題が原因で脅威を受ける可能性があります。 バッファー オーバーランにより、任意のコードが実行できるようになり、その結果認められていない特権の昇格が発生する可能性があるので、バッファー オーバーランの問題はシステムを攻撃するときに使用されることがあります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

C では、これらの関数は、最初の引数の**定数**ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 **Const**へのポインターを受け取るオーバーロードは、 **const**へのポインターを返します。非**const**へのポインターを受け取るバージョンは、非**const**へのポインターを返します。 これらの関数の**const**と**const**以外の両方のバージョンが使用できる場合、マクロ _CRT_CONST_CORRECT_OVERLOADS が定義されます。 両方の C++ オーバーロードに非**定数**の動作が必要な場合は、シンボル _CONST_RETURN を定義します。

出力値は、LC_CTYPE のロケールカテゴリの設定に影響されます。詳細については、「 [setlocale、_wsetlocale](setlocale-wsetlocale.md)」を参照してください。 **_L**サフィックスが付いていないこれらの関数のバージョンは、このロケールに依存する動作に現在のロケールを使用します。**_l**サフィックスが付いているバージョンは、渡されたロケールパラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|
|**該当なし**|**該当なし**|`_mbsstr_l`|**該当なし**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|`strstr`|\<string.h>|
|`wcsstr`|\<string.h> または \<wchar.h>|
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strstr.c

#include <string.h>
#include <stdio.h>

char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int  result;
   printf( "String to be searched:\n   %s\n", string );
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );
   pdest = strstr( string, str );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "%s found at position %d\n", str, result );
   else
      printf( "%s not found\n", str );
}
```

```Output
String to be searched:
   The quick brown dog jumps over the lazy fox
            1         2         3         4         5
   12345678901234567890123456789012345678901234567890

lazy found at position 36
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string:: find](../../standard-library/basic-string-class.md#find)<br/>
