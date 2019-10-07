---
title: wcsrtombs_s
ms.date: 11/04/2016
api_name:
- wcsrtombs_s
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: bd43e4d4bf3a916f83fb014fc85aa5270fbd4c51
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945185"
---
# <a name="wcsrtombs_s"></a>wcsrtombs_s

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
Null 終端文字を含む、変換された文字列のサイズ (バイト単位)。

*mbstr*<br/>
結果として変換されたマルチバイト文字の文字列のバッファーのアドレス。

*sizeInBytes*<br/>
*Mbstr*バッファーのサイズ (バイト単位)。

*wcstr*<br/>
変換するワイド文字の文字列を指します。

*count*<br/>
*Mbstr*バッファーに格納される最大バイト数、または[TRUNCATE](../../c-runtime-library/truncate.md)。

*mbstate*<br/>
**Mbstate_t**の変換状態オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー状況|戻り値と**errno**|
|---------------------|------------------------------|
|*mbstr*が**NULL**で、 *sizeinbytes* > 0|**EINVAL**|
|*wcstr*が**NULL**です|**EINVAL**|
|コピー先のバッファーが小さすぎて、変換された文字列を含めることができません ( *count*が**TRUNCATE**の場合を除きます。次の「解説」を参照してください)。|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の継続が許可された場合、関数はエラーコードを返し、表に示されているように**errno**を設定します。

## <a name="remarks"></a>Remarks

**Wcsrtombs_s**関数は、 *wcstr*が指すワイド文字の文字列を、 *mbstate*に含まれる変換状態を使用して、 *mbstr*が指すバッファーに格納されているマルチバイト文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- ワイド文字の null が検出されました。

- 変換できないワイド文字が検出されました。

- *Mbstr* buffer に格納されているバイト数は*count*と等しくなります。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

*Count*が特別な値の[切り捨て](../../c-runtime-library/truncate.md)である場合、 **wcsrtombs_s**は、null 終端文字用の空きを残したまま、コピー先のバッファーに収まる限りの文字列を変換します。

**Wcsrtombs_s**がソース文字列を正常に変換した場合は、null 終端文字を含む、変換された文字列のサイズが (指定した*preturnvalue* **値が null**ではない)  *&#42;preturnvalue*に配置されます。 これは、 *mbstr*引数が**NULL**の場合にも発生し、必要なバッファーサイズを決定する手段を提供します。 *Mbstr*が**NULL**の場合、 *count*は無視されることに注意してください。

**Wcsrtombs_s**がマルチバイト文字に変換できないワイド文字を検出した場合は、  *\*preturnvalue*に-1 を入れ、コピー先バッファーを空の文字列に設定し、 **errno**を**EILSEQ**に設定して、EILSEQ を返します。

*Wcstr*と*mbstr*が指すシーケンスが重なり合う場合、 **wcsrtombs_s**の動作は未定義になります。 **wcsrtombs_s**は、現在のロケールの LC_TYPE カテゴリの影響を受けます。

> [!IMPORTANT]
> *Wcstr*と*mbstr*が重複しないようにし、その*カウント*に変換するワイド文字の数が正しく反映されていることを確認します。

**Wcsrtombs_s**関数は、 [wcstombs_s、_wcstombs_s_l](wcstombs-s-wcstombs-s-l.md)の再起動によって異なります。 変換状態は、同じまたはその他の再開可能な関数への後続の呼び出しのために*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、 **wcstombs_s**ではなく**wcsrtombs_s**の後続の呼び出しが使用された場合、アプリケーションは**wcslen**ではなく**wcsrlen**を使用します。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcsrtombs_s**関数は、この関数の実行中に現在のスレッドの関数が**setlocale**を呼び出し、 *mbstate*が null の場合は、マルチスレッドセーフです。

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
