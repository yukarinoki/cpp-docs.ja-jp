---
title: _mbccpy_s、_mbccpy_s_l
ms.date: 11/04/2016
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: f9a7554630bd3b46196358c01c21b99978c53e53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575052"
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s、_mbccpy_s_l

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

*buffSizeInBytes*<br/>
コピー先のバッファーのサイズ。

*pCopied*<br/>
コピーされたバイト数が格納されます (正常終了した場合は 1 または 2)。 渡す**NULL**数に関する重要でない場合。

*src*<br/>
コピーするマルチバイト文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 場合*src*または*dest*は**NULL**、数より多い場合、または**buffSizeinBytes**にバイトをコピーするは*dest*、無効なパラメーター ハンドラーが呼び出されます」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 関数を返すかどうかは、引き続き実行が許可された、 **EINVAL**と**errno**に設定されている**EINVAL**します。

## <a name="remarks"></a>Remarks

**_Mbccpy_s**関数からの 1 つのマルチバイト文字のコピー *src*に*dest*します。 場合*src*への暗黙的な呼び出しによって決定されるマルチバイト文字の先行バイトを指していない[_ismbblead](ismbblead-ismbblead-l.md)、1 バイトを*src*へのポインターをコピーします。 場合*src*先行バイトが次のバイトへのポインターには、0 および無効なため、その後に 0 がコピーされます*dest*、 **errno**に設定されている**EILSEQ**、および関数が返される**EILSEQ**します。

**_mbccpy_s** null 終端文字を追加しません。 ただし、場合*src*を null にコピーされますが、null 文字を指す*dest* (これは通常、1 バイトのコピーだけです)。

値*pCopied*コピーされたバイト数が入力されます。 操作が正常に終了した場合は、1 と 2 のどちらかの値となります。 場合**NULL**が渡される、このパラメーターは無視されます。

|*src*|コピー *dest*|*pCopied*|戻り値|
|-----------|----------------------|---------------|------------------|
|先行バイト以外|先行バイト以外|1|0|
|0|0|1|0|
|後続が 0 以外の先行バイト|後続が 0 以外の先行バイト|2|0|
|後続が 0 以外の先行バイト|0|1|**EILSEQ**|

2 行目は、単に 1 行目の特殊なケースです。 表では、メモも*buffSizeInBytes* >= *pCopied*します。

**_mbccpy_s**ロケールに依存する動作に現在のロケールを使用します。 **_mbccpy_s_l**と同じ **_mbccpy_s**する点を除いて **_mbccpy_s_l**の任意のロケールに依存する動作に渡されたロケールを使用します。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|マクロまたはインライン関数に割り当てる。|**_mbccpy_s**|マクロまたはインライン関数に割り当てる。|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
