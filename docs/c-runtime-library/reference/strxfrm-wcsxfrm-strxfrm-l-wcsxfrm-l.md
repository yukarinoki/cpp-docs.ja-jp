---
title: strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc9746d2c98f1799cbdd244e7fc4d465fd705fa
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451720"
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l

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

*strDest*<br/>
対象文字列。

*strSource*<br/>
ソース文字列。

*count*<br/>
配置する文字の最大数*追加される文字*です。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

変換された文字列の長さを返します。終端の null 文字は含まれません。 かどうか、戻り値はより大きいまたは等しい*カウント*では、コンテンツの*追加される文字*は予測できません。 各関数の設定エラーが発生した、 **errno**し、返します**INT_MAX**です。 無効な文字の**errno**に設定されている**EILSEQ**です。

## <a name="remarks"></a>コメント

**Strxfrm**関数が指す文字列を変換*strSource* 、新しい照合に格納されているフォーム*追加される文字*です。 個*カウント*文字で、null 文字は変換され、結果の文字列に配置します。 ロケールを使用して、変換が行われた**LC_COLLATE**カテゴリの設定。 詳細については**LC_COLLATE**を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 **strxfrm** ; そのロケールに依存する動作に現在のロケールを使用 **_strxfrm_l**を除けば、現在のロケールの代わりに渡されたロケールを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

変換後への呼び出し**strcmp**で 2 つの変換された文字列への呼び出しのものと同じ結果が得られます**strcoll 系**元の 2 つの文字列に適用します。 同様に**strcoll 系**と**stricoll**、 **strxfrm**に応じてマルチバイト文字の文字列を自動的に処理します。

**wcsxfrm**のワイド文字バージョンは、 **strxfrm**; の文字列引数**wcsxfrm**ワイド文字のポインターです。 **Wcsxfrm**の後に文字列変換への呼び出し**wcscmp**で 2 つの変換された文字列への呼び出しのものと同じ結果が得られます**wcscoll**に適用します元の 2 つの文字列。 **wcsxfrm**と**strxfrm**それ以外の場合の動作は同じです。 **wcsxfrm** ; そのロケールに依存する動作に現在のロケールを使用 **_wcsxfrm_l**現在のロケールの代わりに渡されたロケールを使用します。

これらの関数では、パラメーターの検証が行われます。 場合*strSource* null ポインターでは、または*追加される文字*は、 **NULL**ポインター (カウントが 0 の場合)、または*カウント*より大きい**INT_MAX**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**返す**INT_MAX**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" ロケールでは、文字セット (ASCII 文字セット) 内の文字の順序は、辞書式文字順序と同じです。 ただし、その他のロケールでは、文字セット内の文字の順序が辞書式文字順序と異なる場合があります。 たとえば、ヨーロッパの一部のロケールで文字 'a' (値 0x61) の前に、文字 ' &\#x00E4;'(値 0xE4)、文字セットが、文字 'ä' の前に、文字 'a' 辞書。

対象の文字セットと辞書式文字順序が異なるロケールで使用して**strxfrm** 、元の文字列にし、 **strcmp**辞書式の文字列を生成するために結果の文字列で現在のロケールに応じて比較**LC_COLLATE**カテゴリの設定。 したがって、上記のロケールの辞書式の 2 つの文字列を比較するには、次のように使用します。 **strxfrm**元の文字列で、 **strcmp**結果の文字列でします。 また、使用することができます**strcoll 系**なく**strcmp**元の文字列にします。

**strxfrm**をラップするラッパーは、基本的に[LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700)で**LCMAP_SORTKEY**です。

次の式の値が保持するために必要な配列のサイズ、 **strxfrm**ソース文字列の変換。

`1 + strxfrm( NULL, string, 0 )`

のみ、"C"ロケールで**strxfrm**は、次に相当します。

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> または \<wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
