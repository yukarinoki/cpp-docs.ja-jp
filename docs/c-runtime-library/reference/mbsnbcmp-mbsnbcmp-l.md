---
title: _mbsnbcmp、_mbsnbcmp_l
ms.date: 11/04/2016
apiname:
- _mbsnbcmp
- _mbsnbcmp_l
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
apitype: DLLExport
f1_keywords:
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
ms.openlocfilehash: 4b21fde122f9804633ac037efaf1f343b5cb9440
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285307"
---
# <a name="mbsnbcmp-mbsnbcmpl"></a>_mbsnbcmp、_mbsnbcmp_l

最初の比較**n** 2 つのマルチバイト文字の文字列のバイト数。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*string1*, *string2*<br/>
比較対象の文字列。

*count*<br/>
比較するバイト数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

戻り値の部分文字列の序数の関係を示す*string1*と*string2*します。

|戻り値|説明|
|------------------|-----------------|
|< 0|*string1*部分文字列より小さい*string2*部分文字列。|
|0|*string1*部分文字列が同じ*string2*部分文字列。|
|> 0|*string1*部分文字列がより大きい*string2*部分文字列。|

パラメーター検証エラー、 **_mbsnbcmp**と **_mbsnbcmp_l**返す**すると**、定義されている\<string.h > と\<mbstring.h >。

## <a name="remarks"></a>Remarks

**_Mbsnbcmp**関数の最初の比較で最も*カウント*バイト*string1*と*string2*を示す値を返すと、これらの部分文字列間のリレーションシップ。 **_mbsnbcmp**の大文字バージョン **_mbsnbicmp**します。 異なり **_mbsnbcoll**、 **_mbsnbcmp**ロケールの照合順序の影響を受けません。 **_mbsnbcmp** 、現在のマルチバイトに従ってマルチバイト文字シーケンスを認識[コード ページ](../../c-runtime-library/code-pages.md)します。

**_mbsnbcmp**よう **_mbsncmp**ことを除いて、 **_mbsncmp**バイトではなく文字で文字列を比較します。

出力値を受ける、 **LC_CTYPE**先行バイトを指定すると、ロケールの設定と末尾のバイトのマルチバイト文字のカテゴリ。 詳細については、「[setlocale](setlocale-wsetlocale.md)」をご覧ください。 **_Mbsnbcmp**関数は、このロケールに依存する動作に現在のロケールを使用します。 **_Mbsnbcmp_l**関数を使用する点を除いて同一です、*ロケール*パラメーター代わりにします。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

いずれか*string1*または*string2* null ポインターの場合は、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 関数を返すかどうかは、引き続き実行が許可された、**すると**と**errno**に設定されている**EINVAL**します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|---------------------------------------|--------------------|-----------------------|
|**_tcsncmp**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcmp**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|
|**_tcsncmp_l**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcml**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcmp**|\<mbstring.h>|
|**_mbsnbcmp_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_mbsnbcmp.c
#include <mbstring.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n          %s\n", string1 );
   printf( "          %s\n\n", string2 );
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );
   result = _mbsncmp( string1, string2 , 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );
   result = _mbsnicmp( string1, string2, 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
}
```

### <a name="output"></a>出力

```Output
Compare strings:
          The quick brown dog jumps over the lazy fox
          The QUICK brown fox jumps over the lazy dog

Function: _mbsnbcmp (first 10 characters only)
Result:   String 1 is greater than string 2

Function: _mbsnicmp _mbsnicmp (first 10 characters only)
Result:   String 1 is equal to string 2
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbicmp、_mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
