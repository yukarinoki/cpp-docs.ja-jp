---
title: _mbclen、mblen、_mblen_l、_mbclen_l
description: Microsoft C ランタイム ライブラリ (CRT) _mbclen、mblen、_mblen_l、および_mbclen_l関数について説明します。
ms.date: 4/2/2020
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
- _o__mbclen
- _o__mbclen_l
- _o__mblen_l
- _o_mblen
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: 76e8771898d8baa65f275304a9aefdcaeeb5b3bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341122"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen、mblen、_mblen_l、_mbclen_l

長さを取得し、マルチバイト文字の有効性を決定します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*\
マルチバイト文字。

*mbstr*\
マルチバイト文字のバイト シーケンスのアドレス。

*カウント*\
チェックするバイト数。

*ロケール*\
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbclen**と **_mbclen_l**は、マルチバイト文字*c*の長さに応じて 1 または 2 を戻します。 *関数は、c が*マルチバイトかどうかに関係なく、UTF-8 の場合は常に 1 を返します。 **_mbclen**にエラーが返されません。

*mbstr*が**NULL**でない場合 **、mblen**と **_mblen_l**はマルチバイト文字の長さをバイト単位で返します。 **mblen**関数と **_mblen_l**関数は UTF-8 で正しく動作し、1 ~ 3 の値を返す場合があります。 *mbstr*が**NULL (** ワイド文字の NULL 文字を指す) の場合 **、mblen**と **_mblen_l は**0 を返します。 *mbstr*が指すオブジェクトは、最初の*カウント*文字内で有効なマルチバイト文字を**形成する必要** **_mblen_l**があります。

## <a name="remarks"></a>解説

**_mbclen**関数は、マルチバイト文字*c*の長さをバイト単位で返します。 *c*がマルチバイト文字の先頭バイトを指していない場合[(_ismbblead](ismbblead-ismbblead-l.md)への**暗黙の呼**び出しによって決まる) _mbclenの結果は予測できません。

**mblen**は、有効なマルチバイト文字の場合は*mbstr*のバイト単位で長さを返します。 また、コード・ページに関連するマルチバイト文字の妥当性も判別します。 **mblen**は*mbstr*に含まれる*数*または少ないバイト数を調べますが **、MB_CUR_MAX**バイト以下です。

出力値は、ロケールの**LC_CTYPE**カテゴリ設定の影響を受けます。 **_l**サフィックスを持たないこれらの関数のバージョンでは、このロケール依存の動作に現在のロケールが使用されます。 **_l**サフィックス付きバージョンは同じように動作しますが、代わりに渡された locale パラメーターを使用します。 詳細については、「 [setlocale](setlocale-wsetlocale.md) 」および「[ロケール](../../c-runtime-library/locale.md)」を参照してください。

**_mbclen**、 **_mblen_l**、および **_mbclen_l**は、標準 C ライブラリの一部ではなく、マイクロソフト固有のライブラリです。 移植可能なコードを使用する場所で使用することはお勧めしません。 標準 C の互換性については **、mblen**または**mbrlen**を代わりに使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|マクロまたはインライン関数にマップされます|**_mbclen**|マクロまたはインライン関数にマップされます|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)\
[ロケール](../../c-runtime-library/locale.md)\
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)\
[_mbccpy、_mbccpy_l](mbccpy-mbccpy-l.md)\
[ムブレン](mbrlen.md)\
[strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
