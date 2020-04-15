---
title: wcrtomb
ms.date: 4/2/2020
api_name:
- wcrtomb
- _o_wcrtomb
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
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: eda857b80404aebe46b090741e0b56d4fe692f34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328097"
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

*Wchar*<br/>
変換するワイド文字。

*mbstate*<br/>
**mbstate_t**オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

変換されたマルチバイト文字を表すのに必要なバイト数を返します。エラーが発生した場合は -1 を返します。

## <a name="remarks"></a>解説

**wcrtomb**関数は *、mbstate*に含まれる指定された変換状態から始まるワイド文字を *、 wchar*に含まれる値から*mbchar*で表されるアドレスに変換します。 戻り値は、対応するマルチバイト文字を表すために必要なバイト数ですが **、MB_CUR_MAX**バイトを超える値は返しません。

*mbstate*が null の場合は *、mbchar*の変換状態を含む内部**mbstate_t**オブジェクトが使用されます。 文字シーケンス*wchar*に対応するマルチバイト文字表現がない場合は、-1 が返され **、errno**が**EILSEQ**に設定されます。

**wcrtomb**関数は、その再起動可能性によって[_wctomb_l wctomb](wctomb-wctomb-l.md)とは異なります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、wcstombs の代わりに**wcsrtombs**への後続の呼び出しを使用した場合、アプリケーションは**wcsnlen**ではなく**wcsrlen**を使用**します**。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="exceptions"></a>例外

**wcrtomb**関数は、この関数が実行中で*mbstate*が null である間に、現在のスレッドで**setlocale**を呼び出す関数がない限り、マルチスレッド セーフです。

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

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
