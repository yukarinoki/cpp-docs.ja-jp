---
title: wcrtomb_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a035010c2af49c0d12b4b7f1d6429c66ba9032cc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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

*呼び出すため*<br/>
ポインター、 **mbstate_t**オブジェクト。

## <a name="return-value"></a>戻り値

0 を返しますまたは、 **errno**値の場合は、エラーが発生します。

## <a name="remarks"></a>コメント

**Wcrtomb_s**関数以降に含まれる指定した変換の状態では、ワイド文字に変換*呼び出すため*に含まれている値から*wchar*にはによって表されるアドレス*mbchar*です。 *PReturnValue*値の変換、バイト数が数になる複数の**MB_CUR_MAX** (バイト単位) またはエラーが発生した場合は、-1。

場合*呼び出すため*が null で、内部**mbstate_t**変換状態を使用します。 文字が含まれる場合*wchar*対応するマルチバイト文字の値を持たない*pReturnValue*は-1 になり、関数は、 **errno**値**EILSEQ**です。

**Wcrtomb_s**関数とは異なります[wctomb_s、_wctomb_s_l](wctomb-s-wctomb-s-l.md)によって、再起動します。 変換状態が格納されている*呼び出すため*以降の呼び出し、同じまたは再開可能なその他の関数にします。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用**後**なく**wcslen**場合、後続の呼び出しには、 **wcsrtombs_s**の代わりに使用された**wcstombs_s**.

C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcrtomb_s**関数が呼び出す関数、現在のスレッドがない限り、マルチ スレッド セーフは**setlocale、_wsetlocale**この関数は実行中に、*呼び出すため*が null です。

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

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
