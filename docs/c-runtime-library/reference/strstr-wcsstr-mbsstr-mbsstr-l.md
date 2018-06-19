---
title: strstr、wcsstr、_mbsstr、_mbsstr_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
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
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbb937cfdce7ed933c637cb48d370515134b66dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415710"
---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr、wcsstr、_mbsstr、_mbsstr_l
文字列で最初に見つかった検索文字列へのポインターを返します。

> [!IMPORTANT]
> **_mbsstr**と **_mbsstr_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

*str*<br/>
NULL で終わる検索対象の文字列。

*テキスト内*<br/>
NULL で終わる検索する文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

最初に見つかった位置のポインターを返します*テキスト内*で*str*、または**NULL**場合*テキスト内*にない*str*. 場合*テキスト内*関数を返します、長さが 0 の文字列を指す*str*です。

## <a name="remarks"></a>コメント

**Strstr**関数は、最初に見つかった位置にポインターを返す*テキスト内*で*str*です。 検索には、終端の NULL 文字は含まれません。 **wcsstr**のワイド文字バージョンは、 **strstr**と **_mbsstr**マルチバイト文字バージョンです。 引数と戻り値の**wcsstr**ワイド文字は、文字列以外の **_mbsstr**マルチバイト文字列です。 **_mbsstr**パラメーターを検証します。 場合*str*または*テキスト内*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合 **_mbsstr**設定**errno**に**EINVAL**は 0 を返します。 **strstr**と**wcsstr**はそのパラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの問題が原因で脅威を受ける可能性があります。 バッファー オーバーランにより、任意のコードが実行できるようになり、その結果認められていない特権の昇格が発生する可能性があるので、バッファー オーバーランの問題はシステムを攻撃するときに使用されることがあります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

C では、これらの関数が受け取る、* * const * *、最初の引数のポインター。 C++ では、2 つのオーバーロードを使用できます。 ポインターを受け取るオーバー ロードは、* * const * * へのポインターを返します**const **; へのポインターを受け取る非**const * * へのポインターを返しますではない**const**です。マクロ **_CRT_CONST_CORRECT_OVERLOADS**場合は、両方が定義されている、 **const * * と非-** const * * これらの関数のバージョンを利用できます。必要な以外の場合**const * * 両方の C++ オーバー ロードの動作のシンボルを定義する **_CONST_RETURN**です。

出力値のロケールのカテゴリの設定の影響を受けた**LC_CTYPE**。 詳細については、を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 これらの関数がないバージョン、 **_l**サフィックスを使用してこのロケールに依存する動作に現在のロケール以外の付いているバージョン、 **_l**代わりに使用する点を除いて、サフィックスは同じ渡されたロケール パラメーター。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsstr**|**strstr**|**_mbsstr**|**wcsstr**|
|**該当なし**|**該当なし**|**_mbsstr_l**|**該当なし**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strstr**|\<string.h>|
|**wcsstr**|\<string.h> または \<wchar.h>|
|**_mbsstr**、 **_mbsstr_l**|\<mbstring.h>|

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
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[basic_string::find](../../standard-library/basic-string-class.md#find)<br/>
