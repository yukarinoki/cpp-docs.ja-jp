---
title: strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l
ms.date: 4/2/2020
api_name:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
- _o__mbspbrk
- _o__mbspbrk_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
ms.openlocfilehash: ecdf896587096f0370351aac07cbd6be57257305
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322169"
---
# <a name="strpbrk-wcspbrk-_mbspbrk-_mbspbrk_l"></a>strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l

文字列をスキャンして、指定された文字セットの文字を検索します。

> [!IMPORTANT]
> `_mbspbrk` および `_mbspbrk_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
NULL で終わる検索対象の文字列。

*strChar セット*<br/>
NULL で終わる文字セット。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*strCharSet*から最初に出現する文字へのポインターを*str*で返します。

## <a name="remarks"></a>解説

str`strpbrk`関数は*strCharSet*の文字セットに*属する文字*の最初の出現箇所へのポインターを返します。 検索には、終端の NULL 文字は含まれません。

`wcspbrk` 関数と `_mbspbrk` 関数は、 `strpbrk`関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcspbrk` 関数の引数と戻り値はワイド文字列で、`_mbspbrk` 関数の引数と戻り値はマルチバイト文字列です。

`_mbspbrk` はそのパラメーターを検証します。 *str*または*strCharSet*が NULL の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合は、NULL を返し、EINVAL`_mbspbrk`に設定`errno`します。 `strpbrk` および `wcspbrk` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

`_mbspbrk` と `_mbscspn` は似ていますが、`_mbspbrk` は [size_t](../../c-runtime-library/standard-types.md) 型の値ではなくポインターを返す点が異なります。

C では、これらの関数は最初の引数の**const**ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 **const**へのポインタを受け取るオーバーロードは **、const**へのポインタを返します。非**const**へのポインターを受け取るバージョンは、非**const**へのポインターを返します。 これらの関数の**const**バージョンと非**const**バージョンの両方が使用可能な場合、マクロ _CRT_CONST_CORRECT_OVERLOADSが定義されます。 両方の C++ オーバーロードに対して非**const**動作が必要な場合は、シンボル _CONST_RETURNを定義します。

出力値は、ロケールのLC_CTYPEカテゴリ設定の設定によって影響されます。詳細については、 [setlocale](setlocale-wsetlocale.md)を参照してください。 **_l**サフィックスを持たないこれらの関数のバージョンでは、このロケール依存の動作に現在のロケールが使用されます。**_l**サフィックスを持つバージョンは、代わりに渡されたロケールパラメータを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|
|**該当なし**|**該当なし**|`_mbspbrk_l`|**該当なし**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|`strpbrk`|\<string.h>|
|`wcspbrk`|\<string.h> または \<wchar.h>|
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr、wcschr、_mbschr、_mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
