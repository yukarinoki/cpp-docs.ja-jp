---
title: wctob
ms.date: 11/04/2016
apiname:
- wctob
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
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: c40fd6a6094aa6f0c8c153bb00420d1e990dbbb2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635484"
---
# <a name="wctob"></a>wctob

ワイド文字がマルチバイト文字に対応し、そのマルチバイト文字の表現を返すかどうかを指定します。

## <a name="syntax"></a>構文

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>パラメーター

*wchar*<br/>
変換される値。

## <a name="return-value"></a>戻り値

場合**wctob**ワイド文字の場合を正常に変換するマルチバイト文字が 1 バイト長である場合にのみ、マルチバイト文字の表現を返します。 場合**wctob**検出すると、マルチバイト文字またはマルチバイト文字に変換できないワイド文字は、完全に 1 バイト長で、-1 を返します。

## <a name="remarks"></a>Remarks

**Wctob**関数に含まれているワイド文字に変換*wchar*を戻り値によって渡される、対応するマルチバイト文字**int**値の場合、マルチバイト文字は、1 バイト長です。

場合**wctob**が失敗して、対応するマルチバイト文字が見つからなかった関数設定**errno**に**EILSEQ** -1 を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムの動作を示しています、 **wcstombs**関数。

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}

```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
