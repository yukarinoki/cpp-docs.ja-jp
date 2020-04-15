---
title: strcat_s、wcscat_s、_mbscat_s、_mbscat_s_l
ms.date: 4/2/2020
api_name:
- strcat_s
- _mbscat_s
- _mbscat_s_l
- wcscat_s
- _o__mbscat_s
- _o__mbscat_s_l
- _o_strcat_s
- _o_wcscat_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strcat_s
- wcscat_s
- _mbscat_s
- _mbscat_s_l
helpviewer_keywords:
- wcscat_s function
- strcat_s function
- mbscat_s function
- strings [C++], appending
- _mbscat_s function
- _mbscat_s_l function
- appending strings
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
ms.openlocfilehash: 458c8ef4c69630b92f39c6ca13a538a1ba7ec72a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355426"
---
# <a name="strcat_s-wcscat_s-_mbscat_s-_mbscat_s_l"></a>strcat_s、wcscat_s、_mbscat_s、_mbscat_s_l

文字列を追加します。 これらのバージョンの [strcat、wcscat、_mbscat](strcat-wcscat-mbscat.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されました。

> [!IMPORTANT]
> **_mbscat_s**および **_mbscat_s_l**は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t strcat_s(
   char *strDestination,
   size_t numberOfElements,
   const char *strSource
);
errno_t wcscat_s(
   wchar_t *strDestination,
   size_t numberOfElements,
   const wchar_t *strSource
);
errno_t _mbscat_s(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource
);
errno_t _mbscat_s_l(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource,
   _locale_t locale
);
template <size_t size>
errno_t strcat_s(
   char (&strDestination)[size],
   const char *strSource
); // C++ only
template <size_t size>
errno_t wcscat_s(
   wchar_t (&strDestination)[size],
   const wchar_t *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s_l(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*strデスティネーション*<br/>
null で終わる追加先の文字列バッファー。

*要素の数*<br/>
追加先の文字列バッファーのサイズ。

*ストソース*<br/>
null で終わる元の文字列バッファー。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*strデスティネーション*|*要素の数*|*ストソース*|戻り値|*strDestination*の内容|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL**または未終了|any|any|**Einval**|変更されない|
|any|any|**NULL**|**Einval**|*str宛先*[0] は 0 に設定されています|
|any|0 または小さすぎる|any|**ERANGE**|*str宛先*[0] は 0 に設定されています|

## <a name="remarks"></a>解説

**strcat_s**関数は*strDestination*に*strSource*を追加し、結果の文字列を null 文字で終了します。 *strSource*の最初の文字は*strDestination*の終端の NULL 文字を上書きします。 **strcat_s**の動作は、ソース文字列とコピー先文字列が重複している場合は定義されません。

2 つ目のパラメーターは、バッファーの残りのサイズではなく、合計サイズであることに注意してください。

```C
char buf[16];
strcpy_s(buf, 16, "Start");
strcat_s(buf, 16, " End");               // Correct
strcat_s(buf, 16 - strlen(buf), " End"); // Incorrect
```

**wcscat_s**と **_mbscat_s**は、**ワイド**文字とマルチバイト文字の strcat_s のバージョンです。 **wcscat_s**の引数と戻り値はワイド文字列です。**_mbscat_s**の文字列はマルチバイト文字文字列です。 それ以外では、これらの関数の動作は同じです。

*strDestination*が null ポインターであるか、null で終わっていない場合、または*strSource*が**NULL**ポインターの場合、または変換先文字列が小さすぎる場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**EINVAL**を返し **、errno**を**EINVAL**に設定します。

**_l**サフィックスを持つ関数のバージョンは同じ動作を持ちますが、現在のロケールの代わりに渡されたロケール パラメーターを使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscat_s**|**strcat_s**|**_mbscat_s**|**wcscat_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strcat_s**|\<string.h>|
|**wcscat_s**|\<string.h> または \<wchar.h>|
|**_mbscat_s**|\<mbstring.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[strcpy_s、wcscpy_s、_mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md) のコード例を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
