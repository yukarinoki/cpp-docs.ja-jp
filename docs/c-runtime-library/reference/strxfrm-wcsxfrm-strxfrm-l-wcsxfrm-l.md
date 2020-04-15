---
title: strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l
ms.date: 4/2/2020
api_name:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
- _o__strxfrm_l
- _o__wcsxfrm_l
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
ms.openlocfilehash: aabe7e7c2e44f558b936e0fd4c6fa4a85dc582f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362971"
---
# <a name="strxfrm-wcsxfrm-_strxfrm_l-_wcsxfrm_l"></a>strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l

ロケール固有の情報に基づいて文字列を変換します。

## <a name="syntax"></a>構文

```C
size_t strxfrm(
   char *strDest,
   const char *strSource,
   size_t count
);
size_t wcsxfrm(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
size_t _strxfrm_l(
   char *strDest,
   const char *strSource,
   size_t count,
   _locale_t locale
);
size_t wcsxfrm_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*最も多くの人*<br/>
対象文字列。

*ストソース*<br/>
ソース文字列。

*count*<br/>
*strDest*に配置する最大文字数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

変換された文字列の長さを返します。終端の null 文字は含まれません。 戻り値が*count*以上の場合は *、strDest*の内容は予測できません。 エラーが発生した場合、各関数は**errno を**設定し、 **INT_MAX**を返します。 無効な文字の場合 **、errno**は**EILSEQ**に設定されます。

## <a name="remarks"></a>解説

**strxfrm**関数は *、strSource*が指す文字列を *、strDest*に格納された新しい照合形式に変換します。 null 文字を含む*count*文字は変換されず、結果の文字列に配置されます。 変換は、ロケールの**LC_COLLATE**カテゴリ設定を使用して行われます。 **LC_COLLATE**の詳細については、「 [setlocale](setlocale-wsetlocale.md)」を参照してください。 **strxfrm**は、ロケール依存の動作に現在のロケールを使用します。**_strxfrm_l**は、現在のロケールの代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

変換後、変換された 2 つの文字列を使用して**strcmp**を呼び出すと、元の 2 つの文字列に適用される**strcoll**呼び出しと同じ結果が得られます。 **strcoll**および**stricoll**と同様に **、strxfrm**は自動的にマルチバイト文字ストリングを適切に処理します。

**wcsxfrm**は **、strxfrm**のワイド文字バージョンです。**wcsxfrm**の文字列引数はワイド文字ポインターです。 **wcsxfrm**では、文字列変換後に、変換された 2 つの文字列を使用して**wcscmp**を呼び出すと、元の 2 つの文字列に適用される**wcscoll**の呼び出しと同じ結果が得られます。 **wcsxfrm**と**strxfrm**は、それ以外の場合と同様に動作します。 **wcsxfrm**は、ロケール依存の動作に現在のロケールを使用します。**_wcsxfrm_l**は、現在のロケールの代わりに渡されたロケールを使用します。

これらの関数では、パラメーターの検証が行われます。 *strSource*が null ポインターの場合、または*strDest*が**NULL**ポインターである場合 (カウントが 0 でない場合)、または*count*が**INT_MAX**より大きい場合は、無効なパラメーター ハンドラーが呼び出[されます。](../../c-runtime-library/parameter-validation.md) 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し **、INT_MAX**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" ロケールでは、文字セット (ASCII 文字セット) 内の文字の順序は、辞書式文字順序と同じです。 ただし、その他のロケールでは、文字セット内の文字の順序が辞書式文字順序と異なる場合があります。 たとえば、ヨーロッパのロケールによっては、文字 'a' (値 0x61) が '&\#x00E4;(値 0xE4) は文字セット内ですが、文字 'ä' は辞書的に文字 'a' の前に付きます。

文字セットと辞書式文字の順序が異なるロケールでは、元の文字列に**strxfrm**を使用し、結果の文字列に**strcmp**を使用して、現在のロケールの**LC_COLLATE**カテゴリ設定に従って辞書式文字列比較を生成します。 したがって、上記のロケールで辞書的に 2 つの文字列を比較するには、元の文字列に**strxfrm**を使用し、結果の文字列を**strcmp**します。 代わりに、元の文字列に**strcmp**ではなく**strcoll**を使用することもできます。

**strxfrm**は基本的に**LCMAP_SORTKEY**を持つ[LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw)のラッパーです。

次の式の値は、変換元文字列の**strxfrm**変換を保持するために必要な配列のサイズです。

`1 + strxfrm( NULL, string, 0 )`

"C" ロケールのみでは **、strxfrm**は次の値と同じです。

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> または \<wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
