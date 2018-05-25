---
title: wcstombs、_wcstombs_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 604ca2d2172e340459d7d5cbf406f01c484750ff
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
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

場合**wcstombs**が正常にマルチバイト文字列を変換します (存在する場合)、終端の null を除く、マルチバイト出力文字列に書き込まれたバイト数を返します。 場合、 *mbstr*引数は**NULL**、 **wcstombs**変換先の文字列のバイト単位で必要なサイズを返します。 場合**wcstombs** 、マルチバイト文字に変換できないワイド文字を検出した型にキャストする-1 を返します**size_t**設定と**errno**に**EILSEQ**.

## <a name="remarks"></a>コメント

**Wcstombs**関数によって示されるワイド文字の文字列に変換*wcstr*に対応するマルチバイト文字し、で結果を格納、 *mbstr*配列。 *カウント*パラメーターは、マルチバイト出力文字列に格納できるバイトの最大数を示します (のサイズは、 *mbstr*)。 通常、ワイド文字列を変換するときに必要になるバイト数は不明です。 出力文字列の 1 バイトだけを必要とするワイド文字もあれば、2 バイトを必要とする文字もあります。 (ワイド文字の null を含む)、入力文字列内のそれぞれのワイド文字をマルチバイト出力文字列に 2 バイトがある場合に合わせて結果が保証されます。

場合**wcstombs**前に、またはとワイド文字の null 文字 (L '\0') が発生した*カウント*に変換する 8 ビット 0 と停止が発生しました。 したがって、マルチバイト文字の文字列で*mbstr*が null で終わる場合にのみ**wcstombs**ワイド null 文字を変換中に発生します。 シーケンスを指す場合*wcstr*と*mbstr*などの動作の重複**wcstombs**が定義されていません。

場合、 *mbstr*引数は**NULL**、 **wcstombs**変換先の文字列のバイト単位で必要なサイズを返します。

**wcstombs**パラメーターを検証します。 場合*wcstr*は**NULL**、または*カウント*がより大きい**INT_MAX**、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は設定**errno**に**EINVAL**し、-1 を返します。

**wcstombs** ; すべてのロケールに依存する動作に現在のロケールを使用 **_wcstombs_l**は、代わりに渡されるロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
