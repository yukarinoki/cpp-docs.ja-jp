---
title: wctomb_s、_wctomb_s_l
ms.date: 4/2/2020
api_name:
- _wctomb_s_l
- wctomb_s
- _o__wctomb_s_l
- _o_wctomb_s
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctomb_s
- _wctomb_s_l
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
ms.openlocfilehash: 63839f70fa334fadd961eb173343d1b406268cfd
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910441"
---
# <a name="wctomb_s-_wctomb_s_l"></a>wctomb_s、_wctomb_s_l

ワイド文字を対応するマルチバイト文字に変換します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [wctomb、_wctomb_l](wctomb-wctomb-l.md) です。

## <a name="syntax"></a>構文

```C
errno_t wctomb_s(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar
);
errno_t _wctomb_s_l(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*この値*<br/>
バイト数、または結果を示すコード。

*mbchar*<br/>
マルチバイト文字のアドレス。

*sizeInBytes*<br/>
バッファー *mbchar*のサイズ。

*wchar*<br/>
ワイド文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

エラー条件

|*mbchar*|*sizeInBytes*|戻り値|*この値*|
|--------------|-------------------|------------------|-----------------|
|**空白**|>0|**EINVAL**|変更されない|
|any|>**INT_MAX**|**EINVAL**|変更されない|
|any|小さすぎる|**EINVAL**|変更されない|

上記のいずれかのエラー条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、 **wctomb**は**einval**を返し、 **errno**を**einval**に設定します。

## <a name="remarks"></a>解説

**Wctomb_s**関数は、 *wchar*引数を対応するマルチバイト文字に変換し、その結果を*mbchar*に格納します。 任意のプログラムの任意のポイントからこの関数を呼び出すことができます。

ワイド文字をマルチバイト文字に変換**wctomb_s**場合は、ワイド文字のバイト数 ( **MB_CUR_MAX**を超えることはありません) が、"" の*値*によって示される整数に格納されます。 *Wchar*がワイド文字の null 文字 (L ' \ 0 ') の場合、 **wctomb_s**に*は1が設定*されます。 ターゲットポインターの*mbchar*が**NULL**の場合、 **wctomb_s**は、の*値*に0を挿入します。 現在のロケールで変換できない場合、 **wctomb_s**は-1 を "の"*値*に入れます。

**wctomb_s**は、ロケールに依存する情報に現在のロケールを使用します。**_wctomb_s_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wctomb_s**|\<stdlib.h>|
|**_wctomb_s_l**|\<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムは、 **wctomb**関数の動作を示しています。

```cpp
// crt_wctomb_s.cpp
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    int i;
    wchar_t wc = L'a';
    char *pmb = (char *)malloc( MB_CUR_MAX );

    printf_s( "Convert a wide character:\n" );
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );
    printf_s( "   Characters converted: %u\n", i );
    printf_s( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[国](../../c-runtime-library/locale.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
