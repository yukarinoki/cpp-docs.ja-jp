---
title: _mbsnbcat、_mbsnbcat_l
ms.date: 4/2/2020
api_name:
- _mbsnbcat_l
- _mbsnbcat
- _o__mbsnbcat
- _o__mbsnbcat_l
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
- mbsnbcat
- mbsnbcat_l
- _mbsnbcat
- _mbsnbcat_l
helpviewer_keywords:
- tcsncat_l function
- _tcsncat function
- mbsnbcat_l function
- mbsnbcat function
- _mbsnbcat_l function
- _tcsncat_l function
- _mbsnbcat function
- tcsncat function
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
ms.openlocfilehash: 7598b20db4698ff8f95fbcefa00864be1b958447
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340812"
---
# <a name="_mbsnbcat-_mbsnbcat_l"></a>_mbsnbcat、_mbsnbcat_l

マルチバイト文字列の最初の**n**バイトを、別の文字列に追加します。 これらの関数のセキュリティを強化したバージョンについては、「[_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)」を参照してください。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned char *_mbsnbcat(
   unsigned char *dest,
   const unsigned char *src,
   size_t count
);
unsigned char *_mbsnbcat_l(
   unsigned char *dest,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char *_mbsnbcat(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsnbcat_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
NULL で終わるマルチバイト文字のコピー先文字列。

*src*<br/>
NULL で終わるマルチバイト文字のコピー元文字列。

*count*<br/>
*src*から*dest*に追加するバイト数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsnbcat**は、変換先文字列へのポインターを返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>解説

**_mbsnbcat**関数は、最大で *、src*の最初の*カウント*バイトを*dest*に追加します。 *dest*の NULL 文字の直前のバイトが先頭バイトの場合 *、src*の最初のバイトはこの先頭バイトを上書きします。 それ以外の場合 *、src*の最初のバイトは*dest*の終端の null 文字を上書きします。 *カウント*バイトが追加される前に*src*に null バイトが出現する場合 **、_mbsnbcat**は*src*から null 文字までのすべてのバイトを追加します。 *count*が*src*の長さより大きい場合は、*カウント*の代わりに*src*の長さが使用されます。 結果の文字列は null 文字で終了します。 重なり合う文字列間でコピーした場合の動作は未定義です。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **関数の_mbsnbcat**バージョンでは、このロケールに依存する動作に現在のロケールが使用されます。**_mbsnbcat_l**バージョンは、代わりに渡されたロケールパラメータを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**セキュリティに関するメモ** null で終わる文字列を使用してください。 null で終わる文字列はターゲット バッファーのサイズを超えないようにしてください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

*dest*または*src*が**NULL**の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター エラーを生成します。 エラーが処理されると、関数は**EINVAL**を返し **、errno**を**EINVAL**に設定します。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_l**|**_strncat_l**|**_mbsnbcat_l**|**_wcsncat_l**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcat**|\<mbstring.h>|
|**_mbsnbcat_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy、_mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbicmp、_mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[_mbsnbset、_mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[_mbsnbcat_s、_mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)<br/>
