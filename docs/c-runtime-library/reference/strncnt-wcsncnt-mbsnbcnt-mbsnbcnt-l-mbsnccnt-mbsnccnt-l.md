---
title: _strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l
ms.date: 11/04/2016
apiname:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
- _mbsnbcnt
- wcsncnt
- _tcsnbcnt
- _mbsnccnt
- _ftcsnbcnt
- mbsnbcnt
- strncnt
- mbsnbcnt_l
- mbsnccnt_l
- mbsnccnt
- _strncnt
- _wcsncnt
helpviewer_keywords:
- _strncnt function
- _mbsnbcnt function
- _mbsnbcnt_l function
- _mbsnccnt_l function
- mbsnbcnt_l function
- mbsnbcnt function
- tcsnbcnt function
- mbsnccnt_l function
- strncnt function
- _tcsnbcnt function
- mbsnccnt function
- wcsncnt function
- _mbsnccnt function
- _wcsncnt function
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
ms.openlocfilehash: 456a11ae98fe8fb40c2ef1d6f4e6d86583f4b7b3
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520215"
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l

指定されたカウント内で文字数またはバイト数を返します。

> [!IMPORTANT]
> **_mbsnbcnt**、 **_mbsnbcnt_l**、 **_mbsnccnt**、および **_mbsnccnt_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
size_t _strncnt(
   const char *str,
   size_t count
);
size_t _wcsncnt(
   const wchar_t *str,
   size_t count
);
size_t _mbsnbcnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnbcnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
size_t _mbsnccnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnccnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
調査する文字列。

*count*<br/>
数の文字またはバイトで調査する*str*します。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsnbcnt**と **_mbsnbcnt_l**見つかったバイト数を返す最初の*カウント*のマルチバイト文字の*str*します。 **_mbsnccnt**と **_mbsnccnt_l**見つかった文字数を返す最初の*カウント*のバイト数の*str*します。 Null 文字が見つかったかどうかは、調査する前に*str*が完了すると、バイトの null 文字の前に見つかった文字数を返します。 場合*str*よりも少ない数で構成されています。*カウント*、文字列内の文字またはバイト数文字またはバイトを返します。 場合*カウント*が小さい 0、0 を返します。 以前のバージョンでは、これらの関数は、型の戻り値を必要がある。 **int**なく**size_t**します。

**_strncnt**最初の文字の数を返します*カウント*1 バイト文字列のバイト*str*します。 **_wcsncnt**最初の文字の数を返します*カウント*ワイド文字の文字列のワイド文字*str*します。

## <a name="remarks"></a>Remarks

**_mbsnbcnt**と **_mbsnbcnt_l**見つかったバイト数をカウントする最初の*カウント*のマルチバイト文字の*str*します。 **_mbsnbcnt**と **_mbsnbcnt_l**置換**mtob**の代わりに使用する必要がありますと**mtob**します。

**_mbsnccnt**と **_mbsnccnt_l**見つかった文字数をカウントする最初の*カウント*のバイト数の*str*します。 場合 **_mbsnccnt**と **_mbsnccnt_l** 2 バイト文字の 2 番目のバイトの null 文字が発生する場合、最初のバイトは null にすることも考慮が返された数の値には含まれません。 **_mbsnccnt**と **_mbsnccnt_l**置換**btom**の代わりに使用する必要がありますと**btom**します。

場合*str*は、 **NULL**ポインター、または*カウント*が 0 の場合」の説明に従って、これらの関数は無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)、 **errno**に設定されている**EINVAL**関数は 0 を返します。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|ルーチンによって返される値|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|N/A|
|**_wcsncnt**|N/A|N/A|**_mbsnbcnt**|
|**_wcsncnt**|N/A|N/A|**_mbsnccnt**|
|N/A|N/A|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_mbsnbcnt.c

#include  <mbstring.h>
#include  <stdio.h>

int main( void )
{
   unsigned char str[] = "This is a multibyte-character string.";
   unsigned int char_count, byte_count;
   char_count = _mbsnccnt( str, 10 );
   byte_count = _mbsnbcnt( str, 10 );
   if ( byte_count - char_count )
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );
   else
      printf( "The first 10 characters are single-byte.\n");
}
```

### <a name="output"></a>出力

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
