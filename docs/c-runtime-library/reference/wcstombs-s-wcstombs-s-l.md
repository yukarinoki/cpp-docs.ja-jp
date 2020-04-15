---
title: wcstombs_s、_wcstombs_s_l
ms.date: 4/2/2020
api_name:
- _wcstombs_s_l
- wcstombs_s
- _o__wcstombs_s_l
- _o_wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
ms.openlocfilehash: c20066cddb3f28d31d2964ec720b64ed49836f65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328045"
---
# <a name="wcstombs_s-_wcstombs_s_l"></a>wcstombs_s、_wcstombs_s_l

ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティが強化されたバージョンの [wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md) です。

## <a name="syntax"></a>構文

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
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
*mbstr*バッファーに格納する最大バイト数 (終端の NULL 文字を含まないか[、_TRUNCATE。](../../c-runtime-library/truncate.md)

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー状態|戻り値と**エラーノ**|
|---------------------|------------------------------|
|*mbstr*は**NULL**で *、サイズは 0 >バイト単位*です|**Einval**|
|*wcstr*は**NULL です**|**Einval**|
|変換後の文字列を格納するには、変換先のバッファが小さすぎます (*カウント*が **_TRUNCATE**場合を除き、下記の「解説」を参照してください)。|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行を続行できる場合、関数はエラー コードを返し、テーブルに示されている**とおり errno**を設定します。

## <a name="remarks"></a>解説

**wcstombs_s**関数は *、wcstr*が指すワイド文字の文字列を *、 mbstr*が指すバッファに格納されているマルチバイト文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- ワイド文字の null が検出されました。

- 変換できないワイド文字が検出されました。

- *mbstr*バッファに格納されているバイト数は*カウント*に等しい。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

*count*が[特殊値_TRUNCATE](../../c-runtime-library/truncate.md)場合 **、wcstombs_s**は、文字列を宛先バッファに収まる限り変換しますが、null ターミネータの空き容量は残ります。 文字列が切り捨てられると、戻り値は**STRUNCATE**になり、変換は成功したと見なされます。

**wcstombs_s**がソース文字列を正常に変換した場合、変換された文字列のサイズ (null 終端文字を含む)*を pReturnValue&#42;* *(pReturnValue*が**NULL**でない場合) に格納します。 これは *、mbstr*引数が**NULL**の場合でも発生し、必要なバッファー サイズを決定する方法を提供します。 *mbstr*が**NULL**の場合、*カウント*は無視されます。

**wcstombs_s**がワイド文字をマルチバイト文字に変換できない場合は *、pReturnValue&#42;* 0 を設定し、宛先バッファを空の文字列に設定し **、errno**を EILSEQ に設定し **、EILSEQ**を返します。 **EILSEQ**

*wcstr*と*mbstr*によって指すシーケンスが重なっている場合 **、wcstombs_s**の動作は未定義です。

> [!IMPORTANT]
> *wcstr*と*mbstr*が重ならないようにし、変換するワイド文字の数*を正しく*反映していることを確認してください。

**wcstombs_s**は、ロケールに依存するすべての動作に現在のロケールを使用します。**_wcstombs_s_l**は、渡されたロケールを代わりに使用することを除けば **、wcstombs**と同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムは **、wcstombs_s**関数の動作を示します。

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s、_wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
