---
title: wcsrtombs_s
ms.date: 4/2/2020
api_name:
- wcsrtombs_s
- _o_wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: 71a2206df9d3afb64fcaf62848988cf116d9071f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328105"
---
# <a name="wcsrtombs_s"></a>wcsrtombs_s

ワイド文字の文字列をマルチバイト文字の文字列形式に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティが強化されたバージョンの [wcsrtombs](wcsrtombs.md) です。

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

*値を返します。*<br/>
変換された文字列のサイズ (null 終端文字を含む) です。

*mbstr*<br/>
結果として変換されたマルチバイト文字の文字列のバッファーのアドレス。

*sizeInBytes*<br/>
*mbstr*バッファーのサイズ (バイト単位)。

*ウストル*<br/>
変換するワイド文字の文字列を指します。

*count*<br/>
*mbstr*バッファーに格納する最大バイト数[(_TRUNCATE)。](../../c-runtime-library/truncate.md)

*mbstate*<br/>
**mbstate_t**変換状態オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー状態|戻り値と**エラーノ**|
|---------------------|------------------------------|
|*mbstr*は**NULL**で *、サイズは 0 >バイト単位*です|**Einval**|
|*wcstr*は**NULL です**|**Einval**|
|変換後の文字列を格納するには、変換先のバッファが小さすぎます (*カウント*が **_TRUNCATE**場合を除き、下記の「解説」を参照してください)。|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行を続行できる場合、関数はエラー コードを返し、テーブルに示されている**とおり errno**を設定します。

## <a name="remarks"></a>解説

**wcsrtombs_s**関数は、 *mbstr*に含まれる変換状態を使用して *、 wcstr*が指すワイド文字のストリングを*mbstr*が指すバッファーに格納されているマルチバイト文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- ワイド文字の null が検出されました。

- 変換できないワイド文字が検出されました。

- *mbstr*バッファに格納されているバイト数は*カウント*に等しい。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

*count*が特殊値[_TRUNCATE](../../c-runtime-library/truncate.md)の場合 **、wcsrtombs_s**は、文字列を宛先バッファに収まる限り変換しますが、null ターミネータの空きは残ります。

**wcsrtombs_s**がソース文字列を正常に変換した場合、変換された文字列のサイズ (null 終端文字を含む) *&#42;pReturnValue*に格納されます *(pReturnValue*が**NULL**でない場合)。 これは *、mbstr*引数が**NULL**の場合でも発生し、必要なバッファー サイズを決定する方法を提供します。 *mbstr*が**NULL**の場合、*カウント*は無視されます。

**wcsrtombs_s**がワイド文字をマルチバイト文字に変換できない場合は*\*、pReturnValue*に -1 を入れ、宛先バッファを空の文字列に設定**し、errno**を EILSEQ に設定し **、EILSEQ**を返します。 **EILSEQ**

*wcstr*と*mbstr*によって指すシーケンスが重なっている場合 **、wcsrtombs_s**の動作は未定義です。 **wcsrtombs_s**は、現在のロケールのLC_TYPEカテゴリの影響を受けます。

> [!IMPORTANT]
> *wcstr*と*mbstr*が重ならないようにし、変換するワイド文字の数*を正しく*反映していることを確認してください。

**wcsrtombs_s**関数は[、wcstombs_sと](wcstombs-s-wcstombs-s-l.md)は異なり、_wcstombs_s_l再起動可能性によって異なります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、wcsrtombs_sへの後続の呼び出しが**wcstombs_s**ではなく **、wcslen**ではなく**wcsrlen**を**使用するとします**。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="exceptions"></a>例外

この関数が実行中に**setlocale**を呼び出す関数が存在しない限り **、wcsrtombs_s**関数はマルチスレッド セーフであり *、mbstate*は null です。

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

int main()
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

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
