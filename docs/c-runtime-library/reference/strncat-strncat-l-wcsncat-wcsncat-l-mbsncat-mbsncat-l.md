---
description: 詳細については、strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l
title: strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l
ms.date: 1/20/2021
api_name:
- strncat
- _strncat_l
- _mbsncat
- _mbsncat_l
- wcsncat
- wcsncat_l
- _o__mbsncat
- _o__mbsncat_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 4b5ae812560cb42498ebed71bb9b8791581ef332
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667024"
---
# <a name="strncat-_strncat_l-wcsncat-_wcsncat_l-_mbsncat-_mbsncat_l"></a>strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l

文字列の文字を追加します。 これらの関数のセキュリティを強化したバージョンについては、「」 (strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) を参照してください `[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l` 。

> [!IMPORTANT]
> **`_mbsncat`** およびは **`_mbsncat_l`** 、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

*`strDest`*\
NULL で終わる追加先の文字列。

*`strSource`*\
NULL で終わる元の文字列。

*`count`*\
追加する文字数。

*`locale`*\
使用するロケール。

## <a name="return-value"></a>戻り値

コピー先文字列へのポインターを返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>注釈

関数は、 **`strncat`** の先頭の最大文字を *`count`* に追加 *`strSource`* *`strDest`* します。 の最初の文字は、 *`strSource`* の終端の null 文字を上書きし *`strDest`* ます。 文字が追加される前にに null 文字が含まれている場合 *`strSource`* *`count`* 、は **`strncat`** null 文字までのすべての文字を追加し *`strSource`* ます。 *`count`* がの長さを超える場合 *`strSource`* 、の *`strSource`* 代わりにの長さが使用され *`count`* ます。 結果の文字列はすべて、null 文字で終了します。 重なり合う文字列間でコピーした場合の動作は未定義です。

> [!IMPORTANT]
> **`strncat`** では、に十分な領域があるかどうかは確認されません。その *`strDest`* ため、バッファーオーバーランの可能性があります。 によって追加される文字数が制限されていることに注意してください *`count`* 。のサイズに制限はありません *`strDest`* 。 次の例を見てください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

**`wcsncat`** と **`_mbsncat`** は、のワイド文字バージョンとマルチバイト文字バージョン **`strncat`** です。 の文字列引数と戻り値はワイド文字列であり、の文字列引数と戻り値 **`wcsncat`** **`_mbsncat`** はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。

出力値は、ロケールのカテゴリの設定に影響され **`LC_CTYPE`** ます。 詳細については、「」を参照してください [`setlocale`](setlocale-wsetlocale.md) 。 サフィックスが付いていないこれらの関数のバージョンは、 **`_l`** このロケールに依存する動作に現在のロケールを使用します。 サフィックスが付いているバージョンは、渡された **`_l`** ロケールパラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|`TCHAR.H `ルーチン|`_UNICODE & _MBCS` 未定義|`_MBCS` れ|`_UNICODE` れ|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_tcsncat`**|**`strncat`**|**`_mbsnbcat`**|**`wcsncat`**|
|**`_tcsncat_l`**|**`_strncat_l`**|**`_mbsnbcat_l`**|**`_wcsncat_l`**|

> [!NOTE]
> **`_strncat_l`** とは **`_wcsncat_l`** ロケールに依存せず、直接呼び出すためのものではありません。 これらは、による内部使用のために用意されてい **`_tcsncat_l`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`strncat`**|\<string.h>|
|**`wcsncat`**|\<string.h> または \<wchar.h>|
|**`_mbsncat`**|\<mbstring.h>|
|**`_mbsncat_l`**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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

**Badappend** によってバッファーオーバーランが発生したことに注意してください。

## <a name="see-also"></a>こちらもご覧ください

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)\
[`_mbsnbcat, _mbsnbcat_l`](mbsnbcat-mbsnbcat-l.md)\
[`strcat, wcscat, _mbscat`](strcat-wcscat-mbscat.md)\
[`strcmp, wcscmp, _mbscmp`](strcmp-wcscmp-mbscmp.md)\
[`strcpy, wcscpy, _mbscpy`](strcpy-wcscpy-mbscpy.md)\
[`strncmp, wcsncmp, _mbsncmp, _mbsncmp_l`](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)\
[`strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l`](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)\
[`_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l`](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)\
[`strrchr, wcsrchr, _mbsrchr, _mbsrchr_l`](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)\
[`_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l`](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)\
[`strspn, wcsspn, _mbsspn, _mbsspn_l`](strspn-wcsspn-mbsspn-mbsspn-l.md)\
[国](../../c-runtime-library/locale.md)\
[Multibyte-Character シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
