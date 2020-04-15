---
title: _mbccpy_s、_mbccpy_s_l
ms.date: 4/2/2020
api_name:
- _mbccpy_s
- _mbccpy_s_l
- _o__mbccpy_s
- _o__mbccpy_s_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
ms.openlocfilehash: 08df395c6978c84b3f53ed0b07ce988afd0249f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341234"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s、_mbccpy_s_l

文字列のマルチバイト文字 1 個を他の文字列にコピーします。 これらのバージョンの [_mbccpy、_mbccpy_l](mbccpy-mbccpy-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」で説明されているように、セキュリティが強化されています。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
コピー先。

*バイト数*<br/>
コピー先のバッファーのサイズ。

*コピー*<br/>
コピーされたバイト数が格納されます (正常終了した場合は 1 または 2)。 数値を気にしない場合は**NULL**を渡します。

*src*<br/>
コピーするマルチバイト文字。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 *src*または*dest*が**NULL**の場合、または**buffSizeinBytes バイト**数が*dest*にコピーされる場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は**EINVAL**を返し **、errno**は**EINVAL**に設定されます。

## <a name="remarks"></a>解説

**_mbccpy_s**関数は、1 つのマルチバイト文字を*src*から*dest*にコピーします。 *src*がマルチバイト文字の先頭バイトを指していない場合は[、 _ismbblead](ismbblead-ismbblead-l.md)への暗黙の呼び出しによって決定される場合 *、src*が指す 1 バイトがコピーされます。 *src*が先頭バイトを指していても、次のバイトが 0 で無効な場合、0 が*dest*にコピーされ **、errno**は**EILSEQ**に設定され、関数は**EILSEQ**を返します。

**_mbccpy_s**は null 終端文字を追加しません。ただし *、src*がヌル文字を指している場合、そのヌルは*dest*にコピーされます (これは単なる通常の 1 バイト・コピーです)。

*pCopied*の値は、コピーされたバイト数で埋められます。 操作が正常に終了した場合は、1 と 2 のどちらかの値となります。 **NULL**が渡された場合、このパラメーターは無視されます。

|*src*|*デスト*にコピー|*コピー*|戻り値|
|-----------|----------------------|---------------|------------------|
|先行バイト以外|先行バイト以外|1|0|
|0|0|1|0|
|後続が 0 以外の先行バイト|後続が 0 以外の先行バイト|2|0|
|後続が 0 以外の先行バイト|0|1|**EILSEQ**|

2 行目は、単に 1 行目の特殊なケースです。 また、この表は*バフサイズインバイトが* >= *コピーされていることを前提としていることに*も注意してください。

**_mbccpy_s**は、ロケールに依存するすべての動作に対して現在のロケールを使用します。 **_mbccpy_s_l**は **_mbccpy_s**と同じですが **、_mbccpy_s_l**はロケールに依存する動作に渡されたロケールを使用します。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|マクロまたはインライン関数に割り当てる。|**_mbccpy_s**|マクロまたはインライン関数に割り当てる。|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
