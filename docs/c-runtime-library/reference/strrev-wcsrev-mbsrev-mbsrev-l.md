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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 585cdae15572eca565d2779225737a014d5f7837
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365038"
---
# <a name="_strrev-_wcsrev-_mbsrev-_mbsrev_l"></a>_strrev、_wcsrev、_mbsrev、_mbsrev_l

文字列の文字を反転させます。

> [!IMPORTANT]
> **_mbsrev**と **_mbsrev_l**は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

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

*Str*<br/>
NULL で終わる反転対象の文字列。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

変更された文字列へのポインターを返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>解説

**_strrev**関数は str の文字の*順序を逆*にします。 終端の NULL 文字はそのまま保持されます。 **_wcsrev**と **_mbsrev**は、ワイド文字とマルチバイト文字の_strrevのバージョン**です**。 **_wcsrev**の引数と戻り値はワイド文字列です。**_mbsrev**の文字列はマルチバイト文字です。 **_mbsrev**の場合 *、str*の各マルチバイト文字のバイトの順序は変更されません。 それ以外では、これらの関数の動作は同じです。

**_mbsrev**パラメーターを検証します。 *string1*または*string2*のいずれかが null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合 **、_mbsrev**は**NULL を**返し **、errno**を**EINVAL**に設定します。 **_strrev**と **_wcsrev**は、パラメーターを検証しません。

出力値は、ロケールの**LC_CTYPE**カテゴリ設定の設定によって影響されます。詳細については[、setlocale を参照_wsetlocale。](setlocale-wsetlocale.md) これらの関数のバージョンは同じですが **、_l**サフィックスを持たない関数は現在のロケールを使用し、**代わりに_l**サフィックスを持つ関数は、渡されたロケール パラメータを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

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
|**_mbsrev**, **_mbsrev_l**|\<mbstring.h>|

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
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
