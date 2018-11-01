---
title: strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l
ms.date: 11/04/2016
apiname:
- strncat
- _strncat_l
- _mbsncat
- _mbsncat_l
- wcsncat
- wcsncat_l
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
- _tcsncat_l
- _wcsncat_l
- _tcsnccat_l
- _mbsncat
- _strncat_l
- strncat
- _tcsnccat
- _mbsncat_l
- _ftcsncat
- wcsncat
- _tcsncat
helpviewer_keywords:
- concatenating strings
- ftcsncat function
- tcsncat_l function
- _tcsnccat_l function
- _tcsncat function
- strncat function
- _ftcsncat function
- mbsncat function
- mbsncat_l function
- strings [C++], appending
- wcsncat function
- tcsnccat function
- tcsnccat_l function
- _tcsnccat function
- string concatenation [C++]
- appending strings
- characters [C++], appending to strings
- _mbsncat function
- _tcsncat_l function
- _mbsncat_l function
- tcsncat function
ms.assetid: de67363b-68c6-4ca5-91e3-478610ad8159
ms.openlocfilehash: 6d44ec9f75ef1c6677c2f6053746592ba6e86382
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574279"
---
# <a name="strncat-strncatl-wcsncat-wcsncatl-mbsncat-mbsncatl"></a>strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l

文字列の文字を追加します。 これらの関数のセキュリティを強化したバージョンについては、「[strncat_s、_strncat_s_l、wcsncat_s、_wcsncat_s_l、_mbsncat_s、_mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)」を参照してください。

> [!IMPORTANT]
> **_mbsncat**と **_mbsncat_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *strncat(
   char *strDest,
   const char *strSource,
   size_t count
);
wchar_t *wcsncat(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
unsigned char *_mbsncat(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count
);
unsigned char *_mbsncat_l(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
char *strncat(
   char (&strDest)[size],
   const char *strSource,
   size_t count
); // C++ only
template <size_t size>
wchar_t *wcsncat(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsncat(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsncat_l(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*strDest*<br/>
NULL で終わる追加先の文字列。

*strSource*<br/>
NULL で終わる元の文字列。

*count*<br/>
追加する文字数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

コピー先文字列へのポインターを返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>Remarks

**Strncat**関数追加、最大で 1 つ目*カウント*の文字*strSource*に*追加される文字*します。 最初の文字の*strSource*の終端の null 文字を上書き*追加される文字*します。 Null 文字が表示される場合*strSource*する前に*カウント*文字が付加されます**strncat**からすべての文字を追加します*strSource*。、null 文字までです。 場合*カウント*がの長さより大きい*strSource*の長さ*strSource*の代わりに使用されます*カウント*します。 結果の文字列はすべて、null 文字で終了します。 重なり合う文字列間でコピーした場合の動作は未定義です。

> [!IMPORTANT]
> **strncat**に十分な領域をチェックしません*追加される文字*; したがってバッファー オーバーランの潜在的な原因です。 注意*カウント*の数を制限文字の追加は、サイズの制限ではなく*追加される文字*します。 下記の例を参照してください。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

**wcsncat**と **_mbsncat**のワイド文字とマルチバイト文字バージョン**strncat**します。 文字列引数と戻り値の**wcsncat**はワイド文字列 **_mbsncat**はマルチバイト文字の文字列。 それ以外では、これらの関数の動作は同じです。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncat**|**strncat**|**_mbsnbcat**|**wcsncat**|
|**_tcsncat_l**|**_strncat_l**|**_mbsnbcat_l**|**_wcsncat_l**|

> [!NOTE]
> **_strncat_l**と **_wcsncat_l**ロケールの依存関係はありません。 して直接呼び出すためのものではありません。 による内部使用に提供されます **_tcsncat_l**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strncat**|\<string.h>|
|**wcsncat**|\<string.h> または \<wchar.h>|
|**_mbsncat**|\<mbstring.h>|
|**_mbsncat_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strncat.c
// Use strcat and strncat to append to a string.
#include <stdlib.h>

#define MAXSTRINGLEN 39

char string[MAXSTRINGLEN+1];
// or char *string = malloc(MAXSTRINGLEN+1);

void BadAppend( char suffix[], int n )
{
   strncat( string, suffix, n );
}

void GoodAppend( char suffix[], size_t n )
{
   strncat( string, suffix, __min( n, MAXSTRINGLEN-strlen(string)) );
}

int main( void )
{
   string[0] = '\0';
   printf( "string can hold up to %d characters\n", MAXSTRINGLEN );

   strcpy( string, "This is the initial string!" );
   // concatenate up to 20 characters...
   BadAppend( "Extra text to add to the string...", 20 );
   printf( "After BadAppend :  %s (%d chars)\n", string, strlen(string) );

   strcpy( string, "This is the initial string!" );
   // concatenate up to 20 characters...
   GoodAppend( "Extra text to add to the string...", 20 );
   printf( "After GoodAppend:  %s (%d chars)\n", string, strlen(string) );
}
```

### <a name="output"></a>出力

```Output
string can hold up to 39 characters
After BadAppend :  This is the initial string!Extra text to add to (47 chars)
After GoodAppend:  This is the initial string!Extra text t (39 chars)
```

なお**BadAppend**バッファー オーバーランが発生します。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[strcat、wcscat、_mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
