---
title: wctob
ms.date: 4/2/2020
api_name:
- wctob
- _o_wctob
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: 420071680c3dc273f6df637cf44273f2c24bd64c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320436"
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

*Wchar*<br/>
変換される値。

## <a name="return-value"></a>戻り値

**wctob**がワイド文字を正常に変換した場合、マルチバイト文字が 1 バイトの長さである場合にのみ、そのマルチバイト文字表現を返します。 **wctob**がワイド文字を検出した場合、マルチバイト文字に変換できないか、マルチバイト文字が正確に 1 バイトの長さでない場合は、-1 を返します。

## <a name="remarks"></a>解説

**wctob**関数は *、wchar*に含まれるワイド文字を、マルチバイト文字が 1 バイトの長さである場合に、戻り**値 int**値によって渡される対応するマルチバイト文字に変換します。

**wctob**が失敗し、対応するマルチバイト文字が見つからなかった場合、関数は**errno**を**EILSEQ**に設定し、-1 を戻します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムは **、wcstombs**関数の動作を示しています。

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
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
