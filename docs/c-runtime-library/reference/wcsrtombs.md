---
title: wcsrtombs
ms.date: 4/2/2020
api_name:
- wcsrtombs
- _o_wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: af22a7d55c5f4958db6962e98f212fb5bb89e61e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328056"
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

*ウストル*<br/>
変換されるワイド文字の文字列の場所を間接的に指します。

*count*<br/>
変換される文字数。

*mbstate*<br/>
**mbstate_t**変換状態オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

正常に変換されたバイト数を返します (null で終了する null バイトがあっても含まれません)。それ以外の場合は、エラーが発生した場合に -1 を返します。

## <a name="remarks"></a>解説

**wcsrtombs**関数は、*指定した変換*状態から始まるワイド文字の文字列を、 wcstr で間接的に指す値から*mbstr*のアドレスに変換*mbstr*します。 null 終端ワイド文字が検出された後、対応しない文字が検出された場合、または次の文字が*count*に含まれる制限を超える場合まで、各文字の変換は継続されます。 **wcsrtombs が***、カウント*が発生する前または時にワイド文字のヌル文字 (L'\0') を検出すると、8 ビット 0 に変換して停止します。

したがって *、mbstr*のマルチバイト文字ストリングは、変換中に**wcsrtombs**がワイド文字のヌル文字を検出した場合にのみ、ヌル終了されます。 *wcstr*と*mbstr*によって指すシーケンスが重なっている場合 **、wcsrtombs**の動作は未定義です。 **wcsrtombs**は、現在のロケールのLC_TYPEカテゴリの影響を受けます。

**wcsrtombs**関数は[、wcstombs](wcstombs-wcstombs-l.md)とは異なり、_wcstombs_l再起動性によって異なります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、wcstombs の代わりに**wcsrtombs**への後続の呼び出しを使用した場合、アプリケーションは**wcsnlen**ではなく**wcsrlen**を使用**します**。

*mbstr*引数が**NULL**の場合 **、wcsrtombs は**、変換先文字列の必要なサイズをバイト単位で返します。 *mbstate*が null の場合、内部**mbstate_t**変換状態が使用されます。 文字シーケンス*wchar*に対応するマルチバイト文字表現がない場合は、-1 が返され **、errno**が**EILSEQ**に設定されます。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="exceptions"></a>例外

**wcsrtombs**関数は、この関数が実行中に**setlocale**を呼び出す関数が存在せず *、mbstate*が null でない限り、マルチスレッド セーフです。

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

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
