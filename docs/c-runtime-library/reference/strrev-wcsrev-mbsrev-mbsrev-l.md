---
title: _strrev、_wcsrev、_mbsrev、_mbsrev_l
ms.date: 4/2/2020
api_name:
- _wcsrev
- _mbsrev
- _strrev
- _mbsrev_l
- _o__mbsrev
- _o__mbsrev_l
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
- _strrev
- _ftcsrev
- _tcsrev
- mbsrev
- mbsrev_l
- _wcsrev_fstrrev
- _mbsrev
helpviewer_keywords:
- _mbsrev_l function
- characters [C++], switching
- _mbsrev function
- strrev function
- _ftcsrev function
- strings [C++], reversing
- wcsrev function
- _strrev function
- mbsrev_l function
- reversing characters in strings
- ftcsrev function
- characters [C++], reversing order
- _wcsrev function
- mbsrev function
- tcsrev function
- _tcsrev function
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
ms.openlocfilehash: d0f03f84045d6fc036e6c8111da7b8484f2b8622
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911154"
---
# <a name="_strrev-_wcsrev-_mbsrev-_mbsrev_l"></a>_strrev、_wcsrev、_mbsrev、_mbsrev_l

文字列の文字を反転させます。

> [!IMPORTANT]
> **_mbsrev**と **_mbsrev_l**は、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *_strrev(
   char *str
);
wchar_t *_wcsrev(
   wchar_t *str
);
unsigned char *_mbsrev(
   unsigned char *str
);
unsigned char *_mbsrev_l(
   unsigned char *str,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*引数*<br/>
NULL で終わる反転対象の文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

変更された文字列へのポインターを返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>解説

**_Strrev**関数は、 *str*の文字の順序を逆にします。 終端の NULL 文字はそのまま保持されます。 **_wcsrev**と **_mbsrev**は **_strrev**のワイド文字バージョンとマルチバイト文字バージョンです。 **_Wcsrev**の引数と戻り値はワイド文字列です。これらの **_mbsrev**はマルチバイト文字列です。 **_Mbsrev**の場合、 *str*の各マルチバイト文字のバイトの順序は変更されません。 それ以外では、これらの関数の動作は同じです。

**_mbsrev**は、そのパラメーターを検証します。 *String1*または*string2*が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **_mbsrev**は**NULL**を返し、 **errno**を**EINVAL**に設定します。 **_strrev**と **_wcsrev**では、パラメーターは検証されません。

出力値は、ロケールの**LC_CTYPE**カテゴリの設定に影響されます。詳細について[は、「setlocale、_wsetlocale](setlocale-wsetlocale.md) 」を参照してください。 これらの関数のバージョンは同じですが、 **_l**サフィックスが付いていないバージョンが現在のロケールを使用し、 **_l**サフィックスが付いているものは、渡されたロケールパラメーターを代わりに使用する点が異なります。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsrev**|**_strrev**|**_mbsrev**|**_wcsrev**|
|**該当なし**|**該当なし**|**_mbsrev_l**|**該当なし**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_strrev**|\<string.h>|
|**_wcsrev**|\<string.h> または \<wchar.h>|
|**_mbsrev**、 **_mbsrev_l**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strrev.c
// This program checks a string to see
// whether it is a palindrome: that is, whether
// it reads the same forward and backward.
//

#include <string.h>
#include <stdio.h>

int main( void )
{
   char* string = "Able was I ere I saw Elba";
   int result;

   // Reverse string and compare (ignore case):
   result = _stricmp( string, _strrev( _strdup( string ) ) );
   if( result == 0 )
      printf( "The string \"%s\" is a palindrome\n", string );
   else
      printf( "The string \"%s\" is not a palindrome\n", string );
}
```

```Output
The string "Able was I ere I saw Elba" is a palindrome
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
