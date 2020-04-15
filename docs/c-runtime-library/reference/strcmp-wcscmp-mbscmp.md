---
title: strcmp、wcscmp、_mbscmp、_mbscmp_l
ms.date: 4/2/2020
api_name:
- wcscmp
- _mbscmp
- _mbscmp_l
- strcmp
- _o__mbscmp
- _o__mbscmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbscmp
- _mbscmp_l
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- _mbscmp_l function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
ms.openlocfilehash: 16bb294f7bbdc0b95b59b845d7b714f823f9d962
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357283"
---
# <a name="strcmp-wcscmp-_mbscmp-_mbscmp_l"></a>strcmp、wcscmp、_mbscmp、_mbscmp_l

文字列を比較します。

> [!IMPORTANT]
> **_mbscmp**と **_mbscmp_l**は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _mbscmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*文字列 1*,*文字列2*<br/>
Null で終わる比較対象の文字列。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各関数の戻り値は *、string1*と*string2*の序数の関係を示します。

|[値]|string1 と string2 との関係|
|-----------|----------------------------------------|
|< 0|*文字列 1*が*文字列 2*より小さい|
|0|*文字列 1*は*文字列 2*と同じです。|
|> 0|*文字列 1*が*文字列 2*より大きい|

パラメーター検証エラーの場合 **、_mbscmp**と **_mbscmp_l**は **_NLSCMPERROR**string.h>\<および\<mbstring.h で定義されている _NLSCMPERROR を返>。

## <a name="remarks"></a>解説

**strcmp**関数は *、string1*と*string2*の序数比較を実行し、それらの関係を示す値を返します。 **wcscmp**と **_mbscmp**は、それぞれ、ワイド文字およびマルチバイト文字バージョンの**strcmp**です。 **_mbscmp**は、現在のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、**エラー_NLSCMPERROR返**します。 **_mbscmp_l**の動作は同じですが、現在のロケールの代わりに渡されたロケール パラメータを使用します。 詳細については、「[コード ページ](../../c-runtime-library/code-pages.md)」を参照してください。 また *、string1*または*string2*が null ポインターの場合は、パラメーター検証で説明されているように **、_mbscmp**は無効なパラメーター ハンドラー[を](../../c-runtime-library/parameter-validation.md)呼び出します。 実行を続行できる場合は **、_mbscmp_mbscmp_l**返**し****、errno**を**EINVAL**に設定して **_NLSCMPERROR。** **strcmp**および**wcscmp**は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**Strcmp**|**_mbscmp**|**wcscmp**|

**strcmp**関数は**strcmp**比較が序数であり、ロケールの影響を受けないという点で**strcoll**関数とは異なります。 **strcoll**は、現在のロケールの**LC_COLLATE**カテゴリを使用して文字列を辞書的に比較します。 **LC_COLLATE**カテゴリの詳細については、「 [setlocale , _wsetlocale](setlocale-wsetlocale.md)」を参照してください。

"C"ロケールでは、文字セット (ASCII 文字セット) 内の文字の順序は、辞書式文字順序と同じです。 ただし、その他のロケールでは、文字セット内の文字の順序が辞書式順序と異なる場合があります。 たとえば、ヨーロッパの一部のロケールでは、文字 'a' (値 0x61) は文字セットで文字 'ä' (値 0xE4) の前にありますが、辞書式の順序では文字 'ä' が文字 'a' の前にあります。

文字セットと辞書式文字の順序が異なるロケールでは、文字列の辞書式比較に**strcmp**の代わりに**strcoll**を使用できます。 または、元の文字列に**strxfrm**を使用し、結果の文字列に**strcmp**を使用することもできます。

**strcmp**関数では、大文字と小文字が区別されます。 stricmp ** \_、wcsicmp**、**\_および mbsicmp**は、最初に小文字の形式に変換して文字列を比較します。 ** \_** ASCII テーブルの 'Z' と 'a' の間にある文字を含む 2 つの\\文字列 ('[,',',''',',','' '\`) は、大文字と小文字の違いに比較します。 たとえば、2 つの文字列 "ABCDE" と "ABCD^" は、比較が小文字 ("abcde" > "abcd^") の場合は一方の方法を比較し、比較が大文字の場合は他の方法 ("ABCDE" < "ABCD^") を比較します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**Strcmp**|\<string.h>|
|**wcscmp**|\<string.h> または \<wchar.h>|
|**_mbscmp**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp、wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp、_memicmp_l](memicmp-memicmp-l.md)<br/>
[関数](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
