---
title: strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l
ms.date: 11/04/2016
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
ms.openlocfilehash: 4e4f5bb6639cbeee0f004f94f09177c08394d43e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258716"
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
配置する文字の最大数*追加される文字*します。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

変換された文字列の長さを返します。終端の null 文字は含まれません。 かどうか、戻り値はより大きいまたは等しい*カウント*、コンテンツの*追加される文字*は予測できません。 各関数の設定エラーが発生、 **errno**返します**INT_MAX**。 無効な文字**errno**に設定されている**EILSEQ**します。

## <a name="remarks"></a>Remarks

**Strxfrm**関数が指す文字列を変換する*strSource*を新しい照合フォームに格納されている*追加される文字*します。 超える*カウント*null 文字を含む文字は変換され、結果の文字列に配置されます。 ロケールを使用して、変換が行われた**LC_COLLATE**カテゴリの設定。 詳細については**LC_COLLATE**を参照してください[setlocale](setlocale-wsetlocale.md)します。 **strxfrm**そのロケールに依存する動作に現在のロケールを使用 **_strxfrm_l**は、現在のロケールの代わりに渡されたロケールを使用すると同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

呼び出し、変換後**strcmp** 2 つの変換された文字列を使用した呼び出しのものと同じ結果が得られます**strcoll 系**元の 2 つの文字列に適用します。 同様**strcoll 系**と**stricoll**、 **strxfrm**として適切なマルチバイト文字の文字列が自動的に処理します。

**wcsxfrm**のワイド文字バージョンは、 **strxfrm**; の文字列引数**wcsxfrm**はワイド文字のポインターです。 **Wcsxfrm**後に、文字列変換の呼び出しを**wcscmp** 2 つの変換された文字列を使用した呼び出しのものと同じ結果が得られます**wcscoll**に適用される、元の 2 つの文字列。 **wcsxfrm**と**strxfrm**動作は同じです。 **wcsxfrm**そのロケールに依存する動作に現在のロケールを使用 **_wcsxfrm_l**現在のロケールの代わりに渡されたロケールを使用します。

これらの関数では、パラメーターの検証が行われます。 場合*strSource* null ポインターの場合は、または*追加される文字*は、 **NULL**ポインター (しない限りカウントがゼロです)、または*カウント*より大きい**INT_MAX**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**戻って**INT_MAX**します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

"C" ロケールでは、文字セット (ASCII 文字セット) 内の文字の順序は、辞書式文字順序と同じです。 ただし、その他のロケールでは、文字セット内の文字の順序が辞書式文字順序と異なる場合があります。 たとえば、ヨーロッパの特定のロケールでは、文字 'a' a (値) の前に文字 ' &\#x00E4;'(0xE4 の値)、文字セットが、文字 'ä' の前に文字 'a' 辞書式。

対象の文字セットと辞書式文字順序が異なるロケールで使用**strxfrm** 、元の文字列にし、 **strcmp**辞書式の文字列を生成するために、結果の文字列に現在のロケールに従って比較**LC_COLLATE**カテゴリの設定。 したがって、上記のロケールの辞書式の 2 つの文字列を比較するには、次のように使用します。 **strxfrm**し、元の文字列で**strcmp** 、結果の文字列にします。 また、使用することができます**strcoll 系**なく**strcmp**元の文字列にします。

**strxfrm**のラッパーでは基本的に[LCMapString](/windows/desktop/api/winnls/nf-winnls-lcmapstringa)で**LCMAP_SORTKEY**します。

次の式の値が保持するために必要な配列のサイズ、 **strxfrm**ソース文字列の変換。

`1 + strxfrm( NULL, string, 0 )`

"C"ロケールのみ、 **strxfrm**は、次に相当します。

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
