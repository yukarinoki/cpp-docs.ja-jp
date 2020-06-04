---
title: _strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l
ms.date: 4/2/2020
api_name:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
- _o__mbsnbcnt
- _o__mbsnbcnt_l
- _o__mbsnccnt
- _o__mbsnccnt_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 020b844d884182ae7553fec9e9db746987189910
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914209"
---
# <a name="_strncnt-_wcsncnt-_mbsnbcnt-_mbsnbcnt_l-_mbsnccnt-_mbsnccnt_l"></a>_strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l

指定されたカウント内で文字数またはバイト数を返します。

> [!IMPORTANT]
> **_mbsnbcnt**、 **_mbsnbcnt_l**、 **_mbsnccnt**、および **_mbsnccnt_l**は、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

*引数*<br/>
調査する文字列。

*count*<br/>
*Str*で調べる文字数またはバイト数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsnbcnt**と **_mbsnbcnt_l**は、 *str*のマルチバイト文字の最初の*カウント*で見つかったバイト数を返します。 **_mbsnccnt**と **_mbsnccnt_l**は、 *str**の最初のバイト数で*見つかった文字数を返します。 *Str*の検査が完了する前に null 文字が検出されると、null 文字の前に見つかったバイト数または文字数が返されます。 *Str*が*カウント*文字またはバイト数未満で構成されている場合は、文字列の文字数またはバイト数を返します。 *Count*が0未満の場合は、0を返します。 以前のバージョンでは、これらの関数には、 **size_t**ではなく**int**型の戻り値がありました。

**_strncnt**は、1バイトの文字列*str*の最初の*count*バイトの文字数を返します。 **_wcsncnt**は、ワイド文字列*str*の最初の文字*数*のワイド文字数を返します。

## <a name="remarks"></a>解説

**_mbsnbcnt**と **_mbsnbcnt_l**は、 *str*のマルチバイト文字の最初の*カウント*で見つかったバイト数をカウントします。 **_mbsnbcnt**と **_mbsnbcnt_l**は**mtob**を置き換え、 **mtob**の代わりに使用する必要があります。

**_mbsnccnt**と **_mbsnccnt_l**は、 *str**の最初のバイト数で*見つかった文字数をカウントします。 **_Mbsnccnt**と **_mbsnccnt_l**が2バイト文字の2番目のバイトで null 文字を検出した場合、最初のバイトも null と見なされ、返されたカウント値には含まれません。 **_mbsnccnt**と **_mbsnccnt_l**は**btom**の代わりに使用する必要が**あります**。

*Str*が**NULL**ポインターまたは*count*が0の場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 **errno**は**EINVAL**に設定され、関数は0を返します。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|ルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|該当なし|
|**_wcsncnt**|該当なし|該当なし|**_mbsnbcnt**|
|**_wcsncnt**|該当なし|該当なし|**_mbsnccnt**|
|該当なし|該当なし|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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
[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
