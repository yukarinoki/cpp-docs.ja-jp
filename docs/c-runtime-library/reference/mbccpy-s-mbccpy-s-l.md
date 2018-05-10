---
title: _mbccpy_s、_mbccpy_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a52314209b62c818623e315757dcd358ec491
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
コピーされたバイト数が格納されます (正常終了した場合は 1 または 2)。 渡す**NULL**数を考慮しない場合。

*src*<br/>
コピーするマルチバイト文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 場合*src*または*dest*は**NULL**、数より多い場合、または**buffSizeinBytes**にバイトをコピーが*dest*、無効なパラメーター ハンドラーが呼び出される」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 関数を返すかどうかは、引き続き実行が許可された、 **EINVAL**と**errno**に設定されている**EINVAL**です。

## <a name="remarks"></a>コメント

**_Mbccpy_s**関数から 1 つのマルチバイト文字をコピーする*src*に*dest*です。 場合*src*への暗黙的な呼び出しによって決定されるマルチバイト文字の先行バイトを指していない[_ismbblead](ismbblead-ismbblead-l.md)、1 バイトを*src*へのポインターをコピーします。 場合*src*先行バイトが後続のバイトへのポインターは 0 と無効ですしたがって、に 0 がコピー *dest*、 **errno**に設定されている**EILSEQ**、および。関数が返される**EILSEQ**です。

**_mbccpy_s**は null 終端文字を追加しません。 ただし、場合*src*に null をコピーし、null 文字を指す*dest* (これは、正規のコピーを 1 バイトだけです)。

値*pCopied*はコピーされたバイト数で塗りつぶされます。 操作が正常に終了した場合は、1 と 2 のどちらかの値となります。 場合**NULL**渡される、このパラメーターは無視されます。

|*src*|コピー *dest*|*pCopied*|戻り値|
|-----------|----------------------|---------------|------------------|
|先行バイト以外|先行バイト以外|1|0|
|0|0|1|0|
|後続が 0 以外の先行バイト|後続が 0 以外の先行バイト|2|0|
|後続が 0 以外の先行バイト|0|1|**EILSEQ**|

2 行目は、単に 1 行目の特殊なケースです。 表では、メモも*buffSizeInBytes* >= *pCopied*です。

**_mbccpy_s**ロケールに依存する動作に現在のロケールを使用します。 **_mbccpy_s_l**と同じ **_mbccpy_s**する点を除いて **_mbccpy_s_l**のすべてのロケールに依存する動作に渡されたロケールを使用します。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|マクロまたはインライン関数に割り当てる。|**_mbccpy_s**|マクロまたはインライン関数に割り当てる。|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
