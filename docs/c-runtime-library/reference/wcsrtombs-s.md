---
title: wcsrtombs_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94e27965d1660f4c344d0026bbfce8685a935c7a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417302"
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
格納されるバイトの最大数、 *mbstr*バッファー、または[_TRUNCATE](../../c-runtime-library/truncate.md)です。

*呼び出すため*<br/>
ポインター、 **mbstate_t**変換状態オブジェクト。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー条件|戻り値と**errno**|
|---------------------|------------------------------|
|*mbstr*は**NULL**と*sizeInBytes* > 0|**EINVAL**|
|*wcstr*は**NULL**|**EINVAL**|
|コピー先のバッファーが小さすぎて、変換された文字列を含める (しない限り、*カウント*は **_TRUNCATE**; 解説を参照してください)|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の継続が許可された場合、関数はエラー コードを返します設定と**errno**表に示すようにします。

## <a name="remarks"></a>コメント

**Wcsrtombs_s**関数によって示されるワイド文字の文字列に変換*wcstr*が指すバッファーに格納されているマルチバイト文字に*mbstr*を使用して、含まれる変換状態*呼び出すため*です。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- ワイド文字の null が検出されました。

- 変換できないワイド文字が検出されました。

- 格納されるバイト数、 *mbstr* equals をバッファー*カウント*です。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

場合*カウント*特殊な値は、 [_TRUNCATE](../../c-runtime-library/truncate.md)、し**wcsrtombs_s** null 用の領域を残して、コピー先のバッファーに収まるようだけでなく、文字列のと同様に変換しますターミネータです。

場合**wcsrtombs_s**ソース文字列を変換が正常に null 終端文字も含めて、変換後の文字列のバイト単位のサイズを入れ *&#42;pReturnValue* (提供*pReturnValue*は**NULL**)。 これが発生した場合でも、 *mbstr*引数は**NULL**し、必要なバッファー サイズを決定する方法を提供します。 場合*mbstr*は**NULL**、*カウント*は無視されます。

場合**wcsrtombs_s** 、マルチバイト文字に変換できないワイド文字を検出した-1 を入れ *\*pReturnValue*、空の文字列をコピー先のバッファーを設定、設定**errno**に**EILSEQ**、し、返します**EILSEQ**です。

シーケンスを指す場合*wcstr*と*mbstr*などの動作の重複**wcsrtombs_s**が定義されていません。 **wcsrtombs_s**は、現在のロケールの LC_TYPE カテゴリの影響を受けます。

> [!IMPORTANT]
> いることを確認*wcstr*と*mbstr*が重なり合わず、および*カウント*に変換するワイド文字の数を正確に反映します。

**Wcsrtombs_s**関数とは異なります[wcstombs_s、_wcstombs_s_l](wcstombs-s-wcstombs-s-l.md)によって、再起動します。 変換状態が格納されている*呼び出すため*以降の呼び出し、同じまたは再開可能なその他の関数にします。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、アプリケーションは使用**後**なく**wcslen**場合、後続の呼び出しには、 **wcsrtombs_s**の代わりに使用された**wcstombs_s**.

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Wcsrtombs_s**関数が呼び出す関数、現在のスレッドがない限り、マルチ スレッド セーフは**setlocale、_wsetlocale**この関数は実行中に、*呼び出すため*が null です。

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

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
