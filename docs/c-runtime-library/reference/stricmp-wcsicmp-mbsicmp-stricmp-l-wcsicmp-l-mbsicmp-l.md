---
title: _stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
dev_langs:
- C++
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0014ea3c727db2a368123696c47df1eca6ba3bb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418329"
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l

文字列の大文字と小文字を区別しない比較を実行します。

> [!IMPORTANT]
> **_mbsicmp**と **_mbsicmp_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _stricmp(
   const char *string1,
   const char *string2
);
int _wcsicmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricmp_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*string1*、 *string2*<br/>
Null で終わる比較対象の文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

戻り値の関係を示す*string1*に*string2*次のようにします。

|戻り値|説明|
|------------------|-----------------|
|< 0|*string1*より小さい*string2*|
|0|*string1*と同じ*string2*|
|> 0|*string1*より大きい*string2*|

エラーが発生した、 **_mbsicmp**返します**すると**で定義されている\<string.h > と\<mbstring.h >。

## <a name="remarks"></a>コメント

**_Stricmp**関数序数に基づく比較*string1*と*string2*との関係を示す値を小文字で返す各文字を変換した後です。 **_stricmp**とは異なります **_stricoll**点で、 **_stricmp**比較がのみ影響を受けました**LC_CTYPE**、どの文字が上限を決定し、小文字します。 **_Stricoll**関数が両方に従って文字列を比較し、 **LC_CTYPE**と**LC_COLLATE**大文字と小文字および照合順序の両方が含まれているロケールのカテゴリ順序です。 詳細については、 **LC_COLLATE**カテゴリを参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)と[ロケールのカテゴリ](../../c-runtime-library/locale-categories.md)です。 この関数のバージョン、 **_l**サフィックスは、ロケールに依存する動作に現在のロケールを使用します。 サフィックスが付いているバージョンは、代わりに渡されたロケールを使用する点を除き、同じです。 ロケールが設定されていない場合は、C ロケールが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

> [!NOTE]
> **_stricmp**は等価 **_strcmpi**です。 同じ意味で使用できますが、 **_stricmp**は標準の優先します。

**_Strcmpi**関数と同じ **_stricmp**旧バージョンとの互換性を保つのために提供されます。

**_Stricmp**は小文字の比較、予期しない動作する可能性があります。

ときに説明するためにで、大文字 **_stricmp**結果に影響の比較には、JOHNSTON と JOHN_HENRY は、2 つの文字列を使用するいると仮定します。 "_" の ASCII 値は小文字の S よりも小さいので、JOHN_HENRY は JOHNSTON よりも小さいとみなされます。実際、91 ～ 96 の ASCII 値を持つ文字はすべて、他の文字よりも小さいと判断されます。

場合、 [strcmp](strcmp-wcscmp-mbscmp.md)関数がの代わりに使用される **_stricmp**JOHN_HENRY は JOHNSTON よりも大きい値を指定します。

**_wcsicmp**と **_mbsicmp**のワイド文字とマルチバイト文字バージョンは、 **_stricmp**です。 引数と戻り値の **_wcsicmp**ワイド文字は、文字列以外の **_mbsicmp**マルチバイト文字列です。 **_mbsicmp**現在のマルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識し、返します**すると**エラーが発生します。 詳細については、「[コード ページ](../../c-runtime-library/code-pages.md)」をご覧ください。 それ以外では、これらの関数の動作は同じです。

**_wcsicmp**と**wcscmp**という点以外の動作は同じ**wcscmp**その引数を比較する前に小文字に変換されません。 **_mbsicmp**と **_mbscmp**という点以外の動作は同じ **_mbscmp**その引数を比較する前に小文字に変換されません。

呼び出す必要があります[setlocale、_wsetlocale](setlocale-wsetlocale.md)の **_wcsicmp** Latin 1 文字を使用します。 既定では、C ロケールが有効になっているので、たとえば、ä は Ä と等しいと見なされません。 呼び出す**setlocale、_wsetlocale**呼び出しの前に、C ロケール以外のロケールで **_wcsicmp**です。 次のサンプルでどのように **_wcsicmp**ロケールは。

```C
// crt_stricmp_locale.c
#include <string.h>
#include <stdio.h>
#include <locale.h>

int main() {
   setlocale(LC_ALL,"C");   // in effect by default
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails
   setlocale(LC_ALL,"");
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds
}
```

呼び出すには、代わりに[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)へのパラメーターとして返されたロケール オブジェクトを渡すと **_wcsicmp_l**です。

これらのすべての関数では、パラメーターの検証が行われます。 いずれか*string1*または*string2*が null ポインターで説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、**すると**設定と**errno**に**EINVAL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_stricmp**、 **_stricmp_l**|\<string.h>|
|**_wcsicmp**、 **_wcsicmp_l**|\<string.h> または \<wchar.h>|
|**_mbsicmp**、 **_mbsicmp_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_stricmp.c

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
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
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
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
