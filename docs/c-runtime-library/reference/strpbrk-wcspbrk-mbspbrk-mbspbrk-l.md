---
title: strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd62d95e971ac5fd927cce1b7b4eb600ebcf7df6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415879"
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l

文字列をスキャンして、指定された文字セットの文字を検索します。

> [!IMPORTANT]
> **_mbspbrk**と **_mbspbrk_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

*str*<br/>
NULL で終わる検索対象の文字列。

*strCharSet*<br/>
NULL で終わる文字セット。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

任意の文字から最初に見つかった位置のポインターを返します*strCharSet*で*str*、または**NULL** 2 つの文字列引数には文字がない共通のポインター。

## <a name="remarks"></a>コメント

**Strpbrk**関数が最初に見つかった位置の文字へのポインターを返します*str*内の文字セットに属している*strCharSet*です。 検索には、終端の NULL 文字は含まれません。

**wcspbrk**と **_mbspbrk**のワイド文字とマルチバイト文字バージョンは、 **strpbrk**です。 引数と戻り値の**wcspbrk**ワイド文字は、文字列以外の **_mbspbrk**マルチバイト文字列です。

**_mbspbrk**パラメーターを検証します。 場合*str*または*strCharSet*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合 **_mbspbrk**返します**NULL**設定と**errno**に**EINVAL**です。 **strpbrk**と**wcspbrk**はそのパラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

**_mbspbrk**に似ていますが **_mbscspn**する点を除いて **_mbspbrk**型の値ではなく、ポインターを返します[size_t](../../c-runtime-library/standard-types.md)です。

C では、これらの関数が受け取る、* * const * *、最初の引数のポインター。 C++ では、2 つのオーバーロードを使用できます。 ポインターを受け取るオーバー ロード * * const * * へのポインターを返します**const **; へのポインターを受け取る非**const * * へのポインターを返しますではない**const**です。マクロ **_CRT_CONST_CORRECT_OVERLOADS**場合は、両方が定義されている、 **const * * と非-** const * * これらの関数のバージョンを利用できます。必要な以外の場合**const * * 両方の C++ オーバー ロードの動作のシンボルを定義する **_CONST_RETURN**です。

出力値の設定の影響を受けた、 **LC_CTYPE**カテゴリ; 詳細については、ロケールの設定、表示[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 この関数のバージョン、 **_l**サフィックスを使用してこのロケールに依存する動作に現在のロケール以外のバージョンで、 **_l**ロケール パラメーターを使用する点を除いて、サフィックスは同じ代わりに渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcspbrk**|**strpbrk**|**_mbspbrk**|**wcspbrk**|
|**該当なし**|**該当なし**|**_mbspbrk_l**|**該当なし**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strpbrk**|\<string.h>|
|**wcspbrk**|\<string.h> または \<wchar.h>|
|**_mbspbrk**、 **_mbspbrk_l**|\<mbstring.h>|

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
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr、wcschr、_mbschr、_mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
