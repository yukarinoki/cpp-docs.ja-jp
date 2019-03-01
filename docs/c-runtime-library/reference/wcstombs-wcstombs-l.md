---
title: wcstombs、_wcstombs_l
ms.date: 11/04/2016
apiname:
- wcstombs
- _wcstombs_l
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
ms.openlocfilehash: d102cd74061faeb0c41823e6cf5c9a8ef335294f
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210732"
---
# <a name="wcstombs-wcstombsl"></a>wcstombs、_wcstombs_l

ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[wcstombs_s、_wcstombs_s_l](wcstombs-s-wcstombs-s-l.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
size_t wcstombs(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count
);
size_t _wcstombs_l(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t wcstombs(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only
template <size_t size>
size_t _wcstombs_l(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*mbstr*<br/>
マルチバイト文字のシーケンスのアドレス。

*wcstr*<br/>
ワイド文字のシーケンスのアドレス。

*count*<br/>
マルチバイト出力文字列に格納できる最大バイト数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

場合**wcstombs**マルチバイト文字列を正常に変換 (ある場合)、終端の null を除く、マルチバイト出力文字列に書き込まれたバイト数を返します。 場合、 *mbstr*引数が**NULL**、 **wcstombs**対象文字列のバイト単位で必要なサイズを返します。 場合**wcstombs**マルチバイト文字に変換できないワイド文字が検出された型にキャストする-1 を返します**size_t**設定と**errno**に**EILSEQ**.

## <a name="remarks"></a>Remarks

**Wcstombs**関数が指すワイド文字の文字列に変換*wcstr*に対応するマルチバイト文字の文字し、に結果を格納、 *mbstr*配列。 *カウント*パラメーターはマルチバイト出力文字列に格納できるバイトの最大数を示します (のサイズは、 *mbstr*)。 通常、ワイド文字列を変換するときに必要になるバイト数は不明です。 出力文字列の 1 バイトだけを必要とするワイド文字もあれば、2 バイトを必要とする文字もあります。 (ワイド文字の null を含む) 入力文字列内のすべてのワイド文字をマルチバイト出力文字列に 2 バイトがある場合は、結果を必ず収まります。

場合**wcstombs**前に、かワイド文字の null 文字 (L '\0') が発生した*カウント*発生するに変換する 8 ビット 0 して停止します。 したがって、マルチバイト文字の文字列*mbstr*が null で終わる場合にのみ**wcstombs**変換中にワイド文字の null 文字を検出するとします。 によって、シーケンスを指している場合*wcstr*と*mbstr*の動作が重なる**wcstombs**が定義されていません。

場合、 *mbstr*引数が**NULL**、 **wcstombs**対象文字列のバイト単位で必要なサイズを返します。

**wcstombs**パラメーターを検証します。 場合*wcstr*は**NULL**、または*カウント*がより大きい**INT_MAX**、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は設定**errno**に**EINVAL** -1 を返します。

**wcstombs**ロケールに依存する動作に現在のロケールを使用 **_wcstombs_l**代わりに渡されたロケールを使用すると同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムの動作を示しています、 **wcstombs**関数。

```C
// crt_wcstombs.c
// compile with: /W3
// This example demonstrates the use
// of wcstombs, which converts a string
// of wide characters to a string of
// multibyte characters.

#include <stdlib.h>
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t  count;
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t *pWCBuffer = L"Hello, world.";

    printf("Convert wide-character string:\n" );

    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s instead
    printf("   Characters converted: %u\n",
            count );
    printf("    Multibyte character: %s\n\n",
           pMBBuffer );

    free(pMBBuffer);
}
```

```Output
Convert wide-character string:
   Characters converted: 13
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
