---
title: wcrtomb | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eca27e81cbb1df26d04059974cdc1ce5313bafa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412678"
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

## <a name="remarks"></a>コメント

**Wcrtomb**関数以降に含まれる指定した変換の状態では、ワイド文字に変換*呼び出すため*に含まれている値から*wchar*にはによって表されるアドレス*mbchar*です。 戻り値は、対応するマルチバイト文字を表すために必要なバイト数が、返すことはできません、複数の**MB_CUR_MAX**バイトです。

場合*呼び出すため*が null で、内部**mbstate_t**オブジェクトの変換状態を含む*mbchar*を使用します。 場合文字シーケンス*wchar*が対応するマルチバイト文字の表現、-1 が返され、 **errno**に設定されている**EILSEQ**です。

**Wcrtomb**関数とは異なります[wctomb、_wctomb_l](wctomb-wctomb-l.md)によって、再起動します。 変換状態が格納されている*呼び出すため*以降の呼び出し、同じまたは再開可能なその他の関数にします。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用**後**なく**wcsnlen**場合、後続の呼び出しには、 **wcsrtombs**の代わりに使用された**wcstombs**.

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcrtomb**関数が呼び出す関数、現在のスレッドがない限り、マルチ スレッド セーフは**setlocale、_wsetlocale**この関数の実行中の場合と中に、*呼び出すため*が null です。

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

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
