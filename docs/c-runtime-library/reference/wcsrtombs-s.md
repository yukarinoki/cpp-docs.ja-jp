---
title: wcsrtombs_s
ms.date: 11/04/2016
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: 9ece21737b1e0b4d157b241286638ac376843fc6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459060"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

ワイド文字の文字列をマルチバイト文字の文字列表現に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティが強化されたバージョンの [wcsrtombs](wcsrtombs.md) です。

## <a name="syntax"></a>構文

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>パラメーター

*pReturnValue*<br/>
変換された文字数。

*mbstr*<br/>
結果として変換されたマルチバイト文字の文字列のバッファーのアドレス。

*sizeInBytes*<br/>
バイト単位のサイズ、 *mbstr*バッファー。

*wcstr*<br/>
変換するワイド文字の文字列を指します。

*count*<br/>
格納されるバイトの最大数、 *mbstr*バッファー、または[_TRUNCATE](../../c-runtime-library/truncate.md)します。

*呼び出すため*<br/>
ポインター、 **mbstate_t**変換状態オブジェクト。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー条件|戻り値および**errno**|
|---------------------|------------------------------|
|*mbstr*は**NULL**と*sizeInBytes* > 0|**EINVAL**|
|*wcstr*は**NULL**|**EINVAL**|
|コピー先のバッファーが小さすぎて変換後の文字列を含む (しない限り、*カウント*は **_TRUNCATE**; 以下の「解説」を参照してください)|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の継続が許可された場合、関数はエラー コードを返します設定と**errno**表に記載されています。

## <a name="remarks"></a>Remarks

**Wcsrtombs_s**関数が指すワイド文字の文字列に変換します*wcstr*が指すバッファーに格納されるマルチバイト文字に*mbstr*を使用して、含まれる変換状態*呼び出すため*します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- ワイド文字の null が検出されました。

- 変換できないワイド文字が検出されました。

- 格納されるバイト数、 *mbstr* equals をバッファー*カウント*します。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

場合*カウント*特殊な値は、 [_TRUNCATE](../../c-runtime-library/truncate.md)、し**wcsrtombs_s**コピー先のバッファーは null の空きを残して収まる限りの文字列の多くに変換されますターミネータ。

場合**wcsrtombs_s** 、元の文字列を正常に変換に null の終端文字を含む変換された文字列のバイト単位のサイズが置かれる *&#42;pReturnValue* (提供されている*pReturnValue*ない**NULL**)。 これが発生した場合でも、 *mbstr*引数が**NULL**し、必要なバッファー サイズを決定する方法を提供します。 その場合*mbstr*は**NULL**、*数*は無視されます。

場合**wcsrtombs_s**マルチバイト文字に変換できないワイド文字が検出されたに-1 を入れ *\*pReturnValue*、空の文字列をコピー先のバッファーを設定、設定**errno**に**EILSEQ**、し、返します**EILSEQ**します。

によって、シーケンスを指している場合*wcstr*と*mbstr*の動作が重なる**wcsrtombs_s**が定義されていません。 **wcsrtombs_s**は現在のロケールの LC_TYPE カテゴリを受けます。

> [!IMPORTANT]
> いることを確認*wcstr*と*mbstr*重複しないと*数*に変換するワイド文字の数を正確に反映します。

**Wcsrtombs_s**関数とは異なります[wcstombs_s、_wcstombs_s_l](wcstombs-s-wcstombs-s-l.md)によってその再起動します。 変換の状態が格納されている*呼び出すため*同じか、またはその他の再開可能な関数を呼び出すのためです。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用**後**なく**wcslen**後続の呼び出しの場合は、 **wcsrtombs_s**の代わりに使用された**wcstombs_s**.

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcsrtombs_s**関数は、現在のスレッドで関数が呼び出すない限り、マルチ スレッド セーフ**setlocale**この関数の実行中に、*呼び出すため*が null です。

## <a name="example"></a>例

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

void main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
