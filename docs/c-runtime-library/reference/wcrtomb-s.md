---
title: wcrtomb_s
ms.date: 4/2/2020
api_name:
- wcrtomb_s
- _o_wcrtomb_s
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
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: ee25b18bfbb86b34e46c8c6776e8ab83157613e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328179"
---
# <a name="wcrtomb_s"></a>wcrtomb_s

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

*値を返します。*<br/>
書き込まれたバイト数を返します。エラーが発生した場合は -1 を返します。

*mbchar*<br/>
結果として得られるマルチバイトに変換された文字。

*サイズオブムチャル*<br/>
*mbchar*変数のサイズ (バイト単位)。

*Wchar*<br/>
変換するワイド文字。

*mbstate*<br/>
**mbstate_t**オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

エラーが発生した場合は、ゼロまたは**errno**値を返します。

## <a name="remarks"></a>解説

**wcrtomb_s**関数は、 *mbstate*に含まれる指定された変換状態から始まるワイド文字を *、 wchar*に含まれる値から*mbchar*で表されるアドレスに変換します。 *pReturnValue*値は、変換されたバイト数ですが **、MB_CUR_MAX**バイト以下、エラーが発生した場合は -1 です。

*mbstate*が null の場合、内部**mbstate_t**変換状態が使用されます。 *wchar*に含まれる文字に対応するマルチバイト文字がない場合 *、pReturnValue*の値は -1 になり、関数は**EILSEQ**の**errno**値を返します。

**wcrtomb_s**関数は[、wctomb_s](wctomb-s-wctomb-s-l.md)とは_wctomb_s_l、再起動可能性によって異なります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、wcsrtombs_sへの後続の呼び出しが**wcstombs_s**ではなく **、wcslen**ではなく**wcsrlen**を**使用するとします**。

C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="exceptions"></a>例外

この関数が実行中で *、mbstate*が null である間、現在のスレッドで**setlocale**を呼び出す関数がない限り **、wcrtomb_s**関数はマルチスレッド セーフです。

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

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
