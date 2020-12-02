---
title: '`_mbsnbcat_s`, `_mbsnbcat_s_l`'
description: Microsoft Visual C++ `_mbsnbcat_s` 、および関数の API の `_mbsnbcat_s_l` 説明
ms.date: 12/2/2020
api_name:
- _mbsnbcat_s_l
- _mbsnbcat_s
- _o__mbsnbcat_s
- _o__mbsnbcat_s_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: c7198d806d8ebe077b423ff2135b5bdcf66ffac6
ms.sourcegitcommit: 9c45483572db4470fe5db5a7b596d5770303098c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "96523115"
---
# <a name="_mbsnbcat_s-_mbsnbcat_s_l"></a>`_mbsnbcat_s`, `_mbsnbcat_s_l`

マルチバイト文字の文字列に、別のマルチバイト文字の文字列の先頭の **n** バイトを追加します。 これらは、「 [CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり[ `_mbsnbcat` `_mbsnbcat_l` 、](mbsnbcat-mbsnbcat-l.md)セキュリティが強化されたバージョンのです。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*`dest`*\
NULL で終わるマルチバイト文字のコピー先文字列。

*`sizeInBytes`*\
バッファーのサイズ *`dest`* (バイト単位)。

*`src`*\
NULL で終わるマルチバイト文字のコピー元文字列。

*`count`*\
からに追加するバイト数 *`src`* *`dest`* 。

*`locale`*\
使用するロケール。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|**`dest`**|*`sizeInBytes`*|*`src`*|戻り値|
|------------|-------------------|-----------|------------------|
|**`NULL`**|any|any|**`EINVAL`**|
|Any|<= 0|any|**`EINVAL`**|
|Any|any|**`NULL`**|**`EINVAL`**|

いずれかのエラー条件が発生すると、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明にあるとおり無効なパラメーター エラーを生成します。 エラーが処理された場合、関数はを返し、 **`EINVAL`** **errno** をに設定し **`EINVAL`** ます。

## <a name="remarks"></a>解説

関数は、 **`_mbsnbcat_s`** *`dest`* の先頭の最大バイトにを追加し *`count`* *`src`* ます。 の null 文字の直前にあるバイト *`dest`* が先頭バイトの場合、の初期バイトによって上書きされ *`src`* ます。 それ以外の場合、の最初のバイトは、 *`src`* の終端の null 文字を上書きし *`dest`* ます。 バイトを追加する前にに null バイトが含まれている場合 *`src`* *`count`* 、は **`_mbsnbcat_s`** null 文字までのすべてのバイトを追加し *`src`* ます。 *`count`* がの長さを超える場合 *`src`* 、の *`src`* 代わりにの長さが使用され *`count`* ます。 結果の文字列は null 文字で終了します。 重なり合う文字列間でコピーした場合の動作は未定義です。

出力値は、ロケールのカテゴリの設定によって影響を受けます **`LC_CTYPE`** 。詳細については [、「setlocale、_wsetlocale](setlocale-wsetlocale.md) 」を参照してください。 サフィックスが付いていないバージョンが現在のロケールを使用し、サフィックスが付いているバージョンが渡されたロケールパラメーターを代わりに使用する点を除いて、これらの関数のバージョンは同じです **`_l`** **`_l`** 。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡略化されています。 オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。また、新しいより安全な関数を自動的に使用して、安全性の低い古い関数を置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグライブラリバージョンは、最初にバッファーを0xFE で埋めます。 この動作を無効にするには、を使用し [`_CrtSetDebugFillThreshold`](crtsetdebugfillthreshold.md) ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|`Tchar.h` ルーチン|`_UNICODE``_MBCS`定義されていない|`_MBCS` れ|`_UNICODE` れ|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**`_tcsncat_s`**|[strncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|**`_mbsnbcat_s`**|[wcsncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|
|**`_tcsncat_s_l`**|**`_strncat_s_l`**|**`_mbsnbcat_s_l`**|**`_wcsncat_s_l`**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`_mbsnbcat_s`**|\<mbstring.h>|
|**`_mbsnbcat_s_l`**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)\
[`_mbsnbcmp`, `_mbsnbcmp_l`](mbsnbcmp-mbsnbcmp-l.md)\
[`_strncnt`, `_wcsncnt`, `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, `_mbsnccnt_l`](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)\
[`_mbsnbcpy`, `_mbsnbcpy_l`](mbsnbcpy-mbsnbcpy-l.md)\
[`_mbsnbcpy_s`, `_mbsnbcpy_s_l`](mbsnbcpy-s-mbsnbcpy-s-l.md)\
[`_mbsnbset`, `_mbsnbset_l`](mbsnbset-mbsnbset-l.md)\
[`strncat`, `_strncat_l`, `wcsncat`, `_wcsncat_l`, `_mbsncat`, `_mbsncat_l`](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)\
[`strncat_s`, `_strncat_s_l`, `wcsncat_s`, `_wcsncat_s_l`, `_mbsncat_s`, `_mbsncat_s_l`](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)
