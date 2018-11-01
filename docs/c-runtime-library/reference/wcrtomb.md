---
title: wcrtomb
ms.date: 11/04/2016
apiname:
- wcrtomb
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
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: a5fad3f41c7ed459a1af3fae7c6a5a85c867d5ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659252"
---
# <a name="wcrtomb"></a>wcrtomb

ワイド文字をマルチバイト文字の表現に変換します。 この関数のセキュリティが強化されたバージョンについては、「[wcrtomb_s](wcrtomb-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>パラメーター

*mbchar*<br/>
結果として得られるマルチバイトに変換された文字。

*wchar*<br/>
変換するワイド文字。

*呼び出すため*<br/>
ポインター、 **mbstate_t**オブジェクト。

## <a name="return-value"></a>戻り値

変換されたマルチバイト文字を表すのに必要なバイト数を返します。エラーが発生した場合は -1 を返します。

## <a name="remarks"></a>Remarks

**Wcrtomb**関数以降に含まれる指定された変換の状態では、ワイド文字に変換*呼び出すため*に含まれている値から*wchar*に、によって表されるアドレス*mbchar*します。 戻り値は、対応するマルチバイト文字を表すために必要なバイト数が、返すことはできません、複数の**MB_CUR_MAX**バイト。

場合*呼び出すため*が null の場合、内部**mbstate_t**オブジェクトの変換状態を含む*mbchar*使用されます。 場合の文字シーケンス*wchar*が対応するマルチバイト文字の表現、-1 が返されます、 **errno**に設定されている**EILSEQ**します。

**Wcrtomb**関数とは異なります[wctomb、_wctomb_l](wctomb-wctomb-l.md)によってその再起動します。 変換の状態が格納されている*呼び出すため*同じか、またはその他の再開可能な関数を呼び出すのためです。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用**後**なく**wcsnlen**後続の呼び出しの場合は、 **wcsrtombs**の代わりに使用された**wcstombs**.

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcrtomb**関数は、現在のスレッドで関数が呼び出すない限り、マルチ スレッド セーフ**setlocale**中に、この関数の実行中に、*呼び出すため*が null です。

## <a name="example"></a>例

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
