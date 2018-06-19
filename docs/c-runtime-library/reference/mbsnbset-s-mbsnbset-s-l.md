---
title: _mbsnbset_s、_mbsnbset_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbset_s_l
- _mbsnbset_s
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
- mbsnbset_s
- _mbsnbset_s_l
- _mbsnbset_s
- mbsnbset_s_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnset_s function
- mbsnbset_s function
- mbsnbset_s_l function
- _mbsnbset_s_l function
- _tcsnset_s_l function
- _mbsnbset_s function
- _tcsnset_s function
- tcsnset_s_l function
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07cbdc979ddd7ba240d9dcaf623d408b8c2681e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404735"
---
# <a name="mbsnbsets-mbsnbsetsl"></a>_mbsnbset_s、_mbsnbset_s_l

最初の設定**n**指定された文字にマルチバイト文字の文字列のバイト数。 これらのバージョンの [_mbsnbset、_mbsnbset_l](mbsnbset-mbsnbset-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _mbsnbset_s(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count
);
errno_t _mbsnbset_s_l(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbset_s(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbset_s_l(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*str*<br/>
変更対象の文字列。

*size*<br/>
文字列バッファーのサイズ。

*c*<br/>
1 バイトまたはマルチバイト文字の設定。

*count*<br/>
設定対象のバイト数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

**_Mbsnbset_s**と **_mbsnbset_s_l**関数設定、多くても 1 つ目*カウント*バイトの*str*に*c*. 場合*カウント*がの長さより大きい*str*の長さ*str*の代わりに使用される*カウント*です。 場合*c*で指定されている最後のバイトに完全に設定することはできず、マルチバイト文字*カウント*、最後のバイトは空白文字で埋められます。 **_mbsnbset_s**と **_mbsnbset_s_l**終端を置かないの末尾に null *str*です。

**_mbsnbset_s**と **_mbsnbset_s_l**のようになります **_mbsnset**これらを設定する点を除いて、*カウント*バイトなく*カウント*文字*c*です。

場合*str*は**NULL**または*カウント*ゼロ、」の説明に従って、この関数は、無効なパラメーター例外を生成[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**です。 また場合、 *c*は有効なマルチバイト文字ではありません**errno**に設定されている**EINVAL**スペースが代わりに使用します。

出力値の設定の影響を受けた、 **LC_CTYPE** 、ロケールのカテゴリの設定; 参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 **_Mbsnbset_s**この関数のバージョンは、このロケールに依存する動作の現在のロケールを使用して、 **_mbsnbset_s_l**バージョンは、ロケール パラメーターを代わりに使用する点を除いて同じです渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset_s**|**_strnset_s**|**_mbsnbset_s**|**_wcsnset_s**|
|**_tcsnset_s_l**|`_strnset_s _l`|**_mbsnbset_s_l**|**_wcsnset_s_l**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbset_s**|\<mbstring.h>|
|**_mbsnbset_s_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_mbsnbset_s.c
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset_s( string, sizeof(string), '*', 4 );
   printf( "After:  %s\n", string );
}
```

## <a name="output"></a>出力

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset、_strnset_l、_wcsnset、_wcsnset_l、_mbsnset、_mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
