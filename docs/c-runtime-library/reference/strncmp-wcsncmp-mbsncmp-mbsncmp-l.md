---
title: strncmp、wcsncmp、_mbsncmp、_mbsncmp_l
ms.date: 4/2/2020
api_name:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
- _o__mbsncmp
- _o__mbsncmp_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
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
ms.openlocfilehash: deae95f8cf7d538dfe22ebbe0e86524765d9d234
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919316"
---
# <a name="strncmp-wcsncmp-_mbsncmp-_mbsncmp_l"></a>strncmp、wcsncmp、_mbsncmp、_mbsncmp_l

2 つの文字列を、指定した文字数まで比較します。

> [!IMPORTANT]
> **_mbsncmp**と **_mbsncmp_l**は、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

戻り値は、次のように、 *string1*と*string2*の部分文字列の関係を示します。

|戻り値|説明|
|------------------|-----------------|
|< 0|*string1* *部分文字列より小さい*文字列文字列|
|0|*string1* substring は*string2* substring と同じ|
|> 0|*string1* *部分文字列より大きい*string1 部分文字列|

パラメーターの検証エラーが発生した場合、 **_mbsncmp**と **_mbsncmp_l**は **_NLSCMPERROR**を\<返します。これは\<、mbstring.h> および> で定義されています。

## <a name="remarks"></a>解説

**Strncmp**関数は、 *string1*と*string2*の最初の最大文字*数の*序数比較を実行し、部分文字列間の関係を示す値を返します。 **strncmp**は **_strnicmp**の大文字と小文字を区別するバージョンです。 **wcsncmp**と **_mbsncmp**は、 **_wcsnicmp**と **_mbsnicmp**の大文字と小文字を区別するバージョンです。

**wcsncmp**と **_mbsncmp**は、 **strncmp**のワイド文字バージョンとマルチバイト文字バージョンです。 **Wcsncmp**の引数はワイド文字列です。これらの **_mbsncmp**はマルチバイト文字列です。 は、マルチバイトのコードページに従ってマルチバイト文字のシーケンスを認識し、エラーが発生した場合に **_NLSCMPERROR**を返します。 **_mbsncmp**

また、 **_mbsncmp**および **_mbsncmp_l**パラメーターを検証します。 *String1*または*string2*が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **_mbsncmp**と **_mbsncmp_l**は **_NLSCMPERROR**を返し、 **errno**を**EINVAL**に設定します。 **strncmp**と**wcsncmp**では、パラメーターは検証されません。 それ以外では、これらの関数の動作は同じです。

**_Mbsncmp**と **_mbsncmp_l**の比較動作は、ロケールの**LC_CTYPE**カテゴリの設定によって影響を受けます。 これは、マルチバイト文字の先頭および末尾のバイトの検出を制御します。 詳細については、「[setlocale](setlocale-wsetlocale.md)」をご覧ください。 **_Mbsncmp**関数は、このロケールに依存する動作に現在のロケールを使用します。 **_Mbsncmp_l**関数は、 *locale*パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。 ロケールが1バイトのロケールの場合、これらの関数の動作は**strncmp**と同じになります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|マクロまたはインライン関数にマップされます|**_mbsncmp**|マクロまたはインライン関数にマップされます|
|**該当なし**|**該当なし**|**_mbsncmp_l**|**該当なし**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strncmp**|\<string.h>|
|**wcsncmp**|\<string.h> または \<wchar.h>|
|**_mbsncmp**、 **_mbsncmp_l**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp、_mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
