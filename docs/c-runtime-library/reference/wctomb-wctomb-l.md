---
title: wctomb、_wctomb_l
ms.date: 11/04/2016
apiname:
- _wctomb_l
- wctomb
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctomb
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
ms.openlocfilehash: b7d7907d14052aead789471bf80f0bc17a457d0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652150"
---
# <a name="wctomb-wctombl"></a>wctomb、_wctomb_l

ワイド文字を対応するマルチバイト文字に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[wctomb_s、_wctomb_s_l](wctomb-s-wctomb-s-l.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int wctomb(
   char *mbchar,
   wchar_t wchar
);
int _wctomb_l(
   char *mbchar,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*mbchar*<br/>
マルチバイト文字のアドレス。

*wchar*<br/>
ワイド文字。

## <a name="return-value"></a>戻り値

場合**wctomb**ワイド文字に変換をマルチバイト文字の場合は、バイト数を返します (よりも大きくなることはありません**MB_CUR_MAX**)、ワイド文字。 場合*wchar*ワイド文字の null 文字 (L '\0') は、 **wctomb** 1 を返します。 場合、ターゲット ポインター *mbchar*は**NULL**、 **wctomb** 0 を返します。 現在のロケールで変換が不可能な場合**wctomb** -1 を返しますと**errno**に設定されている**EILSEQ**します。

## <a name="remarks"></a>Remarks

**Wctomb**関数に変換しますその*wchar*を対応するマルチバイト文字の引数で結果を格納および*mbchar*します。 任意のプログラムの任意のポイントからこの関数を呼び出すことができます。 **wctomb**ロケールに依存する動作に現在のロケールを使用 **_wctomb_l**と同じ**wctomb**を代わりに渡されたロケールを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**wctomb**パラメーターを検証します。 場合*mbchar*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**関数は-1 を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wctomb**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムは、wctomb 関数の動作を示しています。

```cpp
// crt_wctomb.cpp
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int i;
   wchar_t wc = L'a';
   char *pmb = (char *)malloc( MB_CUR_MAX );

   printf( "Convert a wide character:\n" );
   i = wctomb( pmb, wc ); // C4996
   // Note: wctomb is deprecated; consider using wctomb_s
   printf( "   Characters converted: %u\n", i );
   printf( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
