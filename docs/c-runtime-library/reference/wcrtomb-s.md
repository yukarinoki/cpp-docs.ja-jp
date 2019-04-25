---
title: wcrtomb_s
ms.date: 11/04/2016
apiname:
- wcrtomb_s
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
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: 7fe7fba861eecec562928cf381973f62a4db60fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155473"
---
# <a name="wcrtombs"></a>wcrtomb_s

ワイド文字をマルチバイト文字の表現に変換します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [wcrtomb](wcrtomb.md) です。

## <a name="syntax"></a>構文

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>パラメーター

*pReturnValue*<br/>
書き込まれたバイト数を返します。エラーが発生した場合は -1 を返します。

*mbchar*<br/>
結果として得られるマルチバイトに変換された文字。

*sizeOfmbchar*<br/>
サイズ、 *mbchar*変数 (バイト単位)。

*wchar*<br/>
変換するワイド文字。

*mbstate*<br/>
ポインター、 **mbstate_t**オブジェクト。

## <a name="return-value"></a>戻り値

0 を返しますまたは**errno**エラーが発生した場合の値します。

## <a name="remarks"></a>Remarks

**Wcrtomb_s**関数以降に含まれる指定された変換の状態では、ワイド文字に変換*呼び出すため*に含まれている値から*wchar*に、によって表されるアドレス*mbchar*します。 *PReturnValue*値になりますが、変換されたバイトの数以上の**MB_CUR_MAX** (バイト単位) またはエラーが発生した場合、-1。

場合*呼び出すため*が null の場合、内部**mbstate_t**変換状態を使用します。 文字が含まれている場合*wchar*対応するマルチバイト文字の値を持たない*pReturnValue*は-1 になり、関数は、 **errno**値**EILSEQ**します。

**Wcrtomb_s**関数とは異なります[wctomb_s、_wctomb_s_l](wctomb-s-wctomb-s-l.md)によってその再起動します。 変換の状態が格納されている*呼び出すため*同じか、またはその他の再開可能な関数を呼び出すのためです。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用**後**なく**wcslen**後続の呼び出しの場合は、 **wcsrtombs_s**の代わりに使用された**wcstombs_s**.

C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcrtomb_s**関数は、現在のスレッドで関数が呼び出すない限り、マルチ スレッド セーフ**setlocale**この関数の実行中に、*呼び出すため*が null です。

## <a name="example"></a>例

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
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
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
