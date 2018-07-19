---
title: strncmp、wcsncmp、_mbsncmp、_mbsncmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
dev_langs:
- C++
helpviewer_keywords:
- _tcsnccmp function
- ftcsncmp function
- wcsncmp function
- _ftcsncmp function
- _mbsncmp function
- tcsncmp function
- mbsncmp function
- _mbsncmp_l function
- mbsncmp_l function
- strncmp function
- strings [C++], comparing characters of
- string comparison [C++], strncmp function
- _tcsncmp function
- tcsnccmp function
- ftcsnccmp function
- characters [C++], comparing
- _ftcsnccmp function
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a64d7248151287f4f2af38e666db62f9a15d833f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417354"
---
# <a name="strncmp-wcsncmp-mbsncmp-mbsncmpl"></a>strncmp、wcsncmp、_mbsncmp、_mbsncmp_l

2 つの文字列を、指定した文字数まで比較します。

> [!IMPORTANT]
> **_mbsncmp**と **_mbsncmp_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int strncmp(
   const char *string1,
   const char *string2,
   size_t count
);
int wcsncmp(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsncmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsncmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*string1*、 *string2*<br/>
比較する文字列。

*count*<br/>
比較する文字数

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

戻り値の部分文字列の関係を示す*string1*と*string2*次のようにします。

|戻り値|説明|
|------------------|-----------------|
|< 0|*string1*部分文字列より小さい*string2*部分文字列|
|0|*string1*部分文字列と同じ*string2*部分文字列|
|> 0|*string1*部分文字列より大きい*string2*部分文字列|

パラメーター検証エラーが発生した、 **_mbsncmp**と **_mbsncmp_l**返す**すると**で定義されている\<string.h > と\<mbstring.h >。

## <a name="remarks"></a>コメント

**Strncmp**関数は、最大で 1 つ目の序数に基づく比較を実行*カウント*内の文字*string1*と*string2*と部分文字列の関係を示す値を返します。 **strncmp**のバージョンが大文字小文字を区別 **_strnicmp**です。 **wcsncmp**と **_mbsncmp**のバージョンが大文字小文字を区別 **_wcsnicmp**と **_mbsnicmp**です。

**wcsncmp**と **_mbsncmp**のワイド文字とマルチバイト文字バージョンは、 **strncmp**です。 引数**wcsncmp**ワイド文字は、文字列以外の **_mbsncmp**マルチバイト文字列です。 **_mbsncmp**マルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識し、返します**すると**エラーが発生します。

また、 **_mbsncmp**と **_mbsncmp_l**パラメーターを検証します。 場合*string1*または*string2* null ポインターで説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合 **_mbsncmp**と **_mbsncmp_l**返す**すると**設定と**errno**に**EINVAL**です。 **strncmp**と**wcsncmp**はそのパラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

比較の動作の **_mbsncmp**と **_mbsncmp_l**の設定は、影響を受ける、 **LC_CTYPE**ロケールのカテゴリの設定。 これは、マルチバイト文字の先頭および末尾のバイトの検出を制御します。 詳細については、「[setlocale](setlocale-wsetlocale.md)」をご覧ください。 **_Mbsncmp**関数は、このロケールに依存する動作に現在のロケールを使用します。 **_Mbsncmp_l**関数は、使用する点を除いて同一です、*ロケール*パラメーター代わりにします。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。 これらの関数の動作と同じロケールが 1 バイトのロケールの場合は、 **strncmp**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|マクロまたはインライン関数にマップされます|**_mbsncmp**|マクロまたはインライン関数にマップされます|
|**該当なし**|**該当なし**|**_mbsncmp_l**|**該当なし**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strncmp**|\<string.h>|
|**wcsncmp**|\<string.h> または \<wchar.h>|
|**_mbsncmp**、 **_mbsncmp_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strncmp.c
#include <string.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n      %s\n      %s\n\n",
           string1, string2 );
   printf( "Function:   strncmp (first 10 characters only)\n" );
   result = strncmp( string1, string2 , 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n\n", tmp );
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );
   result = _strnicmp( string1, string2, 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
      The quick brown dog jumps over the lazy fox
      The QUICK brown fox jumps over the lazy dog

Function:   strncmp (first 10 characters only)
Result:      String 1 is greater than string 2

Function:   strnicmp _strnicmp (first 10 characters only)
Result:      String 1 is equal to string 2
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp、_mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
