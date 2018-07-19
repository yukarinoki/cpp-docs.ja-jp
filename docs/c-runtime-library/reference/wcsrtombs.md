---
title: wcsrtombs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsrtombs
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
- wcsrtombs
dev_langs:
- C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2ea0252714803fe8cad48635486d2011275407
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415469"
---
# <a name="wcsrtombs"></a>wcsrtombs

ワイド文字の文字列をマルチバイト文字の文字列形式に変換します。 この関数のセキュリティが強化されたバージョンについては、「[wcsrtombs_s](wcsrtombs-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>パラメーター

*mbstr*<br/>
結果として変換されたマルチバイト文字のアドレスの場所。

*wcstr*<br/>
変換されるワイド文字の文字列の場所を間接的に指します。

*count*<br/>
変換される文字数。

*呼び出すため*<br/>
ポインター、 **mbstate_t**変換状態オブジェクト。

## <a name="return-value"></a>戻り値

正常に変換されたバイト数を返します (null で終了する null バイトがあっても含まれません)。それ以外の場合は、エラーが発生した場合に -1 を返します。

## <a name="remarks"></a>コメント

**Wcsrtombs**関数以降に含まれる指定した変換の状態では、ワイド文字の文字列に変換*呼び出すため*で指す間接の値から*wcstr*のアドレスに*mbstr*です。 までの各文字に対して変換が続きます。 null ワイド文字が検出された後、対応する文字が検出されたときに、または次の文字は、に格納されている上限を超えてしまいます*カウント*です。 場合**wcsrtombs**前に、またはとワイド文字の null 文字 (L '\0') が発生した*カウント*発生すると、8 ビット 0 と停止に変換します。

したがって、マルチバイト文字の文字列で*mbstr*が null で終わる場合にのみ**wcsrtombs**ワイド null 文字を変換中に発生します。 シーケンスを指す場合*wcstr*と*mbstr*などの動作の重複**wcsrtombs**が定義されていません。 **wcsrtombs**は、現在のロケールの LC_TYPE カテゴリの影響を受けます。

**Wcsrtombs**関数とは異なります[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)によって、再起動します。 変換状態が格納されている*呼び出すため*以降の呼び出し、同じまたは再開可能なその他の関数にします。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションは使用**後**なく**wcsnlen**場合、後続の呼び出しには、 **wcsrtombs**の代わりに使用された**wcstombs**.

場合、 *mbstr*引数は**NULL**、 **wcsrtombs**変換先の文字列のバイト単位で必要なサイズを返します。 場合*呼び出すため*が null で、内部**mbstate_t**変換状態を使用します。 場合文字シーケンス*wchar*が対応するマルチバイト文字の表現、-1 が返され、 **errno**に設定されている**EILSEQ**です。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcsrtombs**関数が呼び出す関数、現在のスレッドがない限り、マルチ スレッド セーフは**setlocale、_wsetlocale**この関数は実行中に、*呼び出すため*が null でないです。

## <a name="example"></a>例

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
