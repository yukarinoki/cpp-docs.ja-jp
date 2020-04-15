---
title: wcstombs、_wcstombs_l
ms.date: 4/2/2020
api_name:
- wcstombs
- _wcstombs_l
- _o__wcstombs_l
- _o_wcstombs
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: fb95c6d73a3979a39995b9104a76fc42ca9e8535
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366718"
---
# <a name="wcstombs-_wcstombs_l"></a>wcstombs、_wcstombs_l

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

*ウストル*<br/>
ワイド文字のシーケンスのアドレス。

*count*<br/>
マルチバイト出力文字列に格納できる最大バイト数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**wcstombs**がマルチバイト文字列の変換に成功した場合、終端の null を除いて、マルチバイト出力文字列に書き込まれたバイト数を返します。. *mbstr*引数が**NULL**の場合 **、wcstombs は**、変換先文字列の必要なサイズをバイト単位で返します。 **wcstombs**がワイド文字を検出した場合、マルチバイト文字に変換できない場合は **、-1**キャストを size_t 型に戻し **、errno**を**EILSEQ**に設定します。

## <a name="remarks"></a>解説

**wcstombs**関数は *、wcstr*が指すワイド文字ストリングを対応するマルチバイト文字に変換し、その結果を*mbstr*配列に格納します。 *count*パラメーターは、マルチバイト出力文字列に格納できる最大バイト数 (つまり*mbstr*のサイズ) を示します。 通常、ワイド文字列を変換するときに必要になるバイト数は不明です。 出力文字列の 1 バイトだけを必要とするワイド文字もあれば、2 バイトを必要とする文字もあります。 入力文字列内のワイド文字 (ワイド文字 null を含む) ごとにマルチバイト出力文字列に 2 バイトが含まれている場合、結果は必ず収まります。

**wcstombs は***、カウント*が発生する前またはカウント時にワイド文字のヌル文字 (L'\0') を検出すると、8 ビット 0 に変換して停止します。 したがって、変換中に**wcstombs**がワイド文字のヌル文字を検出した場合にのみ *、mbstr*のマルチバイト文字ストリングは NULL で終わります。 *wcstr*と*mbstr*によって指すシーケンスが重なっている場合 **、wcstombs**の動作は未定義です。

*mbstr*引数が**NULL**の場合 **、wcstombs は**、変換先文字列の必要なサイズをバイト単位で返します。

**wcstombs はその**パラメータを検証します。 *wcstr*が**NULL**の場合、または*count*が**INT_MAX**より大きい場合、この関数は、パラメーター[の検証](../../c-runtime-library/parameter-validation.md)で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、関数は**errno**を**EINVAL**に設定し、-1 を返します。

**wcstombs は**ロケールに依存する動作に現在のロケールを使用します。**_wcstombs_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムは **、wcstombs**関数の動作を示しています。

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
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
