---
title: wcsrtombs
ms.date: 11/04/2016
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
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: 46ef195ec4685c327c4b5951ec44e5c363214b59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155330"
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

*mbstate*<br/>
ポインター、 **mbstate_t**変換状態オブジェクト。

## <a name="return-value"></a>戻り値

正常に変換されたバイト数を返します (null で終了する null バイトがあっても含まれません)。それ以外の場合は、エラーが発生した場合に -1 を返します。

## <a name="remarks"></a>Remarks

**Wcsrtombs**関数に含まれる指定された変換の状態で始まるワイド文字の文字列を変換する*呼び出すため*で指す間接の値から*wcstr*のアドレスに*mbstr*します。 まで、各文字の変換が継続されます。 対応しない文字が検出されたときに、null で終了するワイド文字が検出された後、または次の文字はに含まれている上限を超える場合*カウント*します。 場合**wcsrtombs**前に、かワイド文字の null 文字 (L '\0') が発生した*カウント*発生するに変換する 8 ビット 0 して停止します。

したがって、マルチバイト文字の文字列*mbstr*が null で終わる場合にのみ**wcsrtombs**変換中にワイド文字の null 文字を検出するとします。 によって、シーケンスを指している場合*wcstr*と*mbstr*の動作が重なる**wcsrtombs**が定義されていません。 **wcsrtombs**は現在のロケールの LC_TYPE カテゴリを受けます。

**Wcsrtombs**関数とは異なります[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)によってその再起動します。 変換の状態が格納されている*呼び出すため*同じか、またはその他の再開可能な関数を呼び出すのためです。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションは使用**後**なく**wcsnlen**後続の呼び出しの場合は、 **wcsrtombs**の代わりに使用された**wcstombs**.

場合、 *mbstr*引数が**NULL**、 **wcsrtombs**対象文字列のバイト単位で必要なサイズを返します。 場合*呼び出すため*が null の場合、内部**mbstate_t**変換状態を使用します。 場合の文字シーケンス*wchar*が対応するマルチバイト文字の表現、-1 が返されます、 **errno**に設定されている**EILSEQ**します。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcsrtombs**関数は、現在のスレッドで関数が呼び出すない限り、マルチ スレッド セーフ**setlocale**この関数の実行中に、*呼び出すため*が null でないです。

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

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
