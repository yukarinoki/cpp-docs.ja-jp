---
title: strrchr、wcsrchr、_mbsrchr、_mbsrchr_l
ms.date: 4/2/2020
api_name:
- strrchr
- wcsrchr
- _mbsrchr
- _mbsrchr_l
- _o__mbsrchr
- _o__mbsrchr_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsrchr
- _ftcsrchr
- strrchr
- wcsrchr
- _mbsrchr
helpviewer_keywords:
- _mbsrchr function
- tcsrchr function
- mbsrchr_l function
- characters [C++], scanning for
- ftcsrchr function
- _tcsrchr function
- strings [C++], scanning
- mbsrchr function
- strrchr function
- scanning strings
- wcsrchr function
- _ftcsrchr function
- _mbsrchr_l function
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
ms.openlocfilehash: 2475eab34c6a18b3dc7a8a15145c184cea543aee
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911160"
---
# <a name="strrchr-wcsrchr-_mbsrchr-_mbsrchr_l"></a>strrchr、wcsrchr、_mbsrchr、_mbsrchr_l

文字列をスキャンして最後に出現する文字を検索します。

> [!IMPORTANT]
> `_mbsrchr` および `_mbsrchr_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *strrchr(
   const char *str,
   int c
); // C only
char *strrchr(
   char *str,
   int c
); // C++ only
const char *strrchr(
   const char *str,
   int c
); // C++ only
wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C only
wchar_t *wcsrchr(
   wchar_t *str,
   wchar_t c
); // C++ only
const wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C++ only
unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C only
unsigned char *_mbsrchr(
   unsigned char *str,
   unsigned int c
); // C++ only
const unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C++ only
unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C only
unsigned char *_mbsrchr_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
const unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*引数*<br/>
NULL で終わる検索対象の文字列。

*40u-c*<br/>
検索する文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*Str*で*c*が最後に出現する位置へのポインターを返すか、 *c*が見つからない場合は NULL を返します。

## <a name="remarks"></a>解説

関数`strrchr`は、 *str*で最後に出現した*c* ( **char**型に変換) を検索します。 検索には、終端の null 文字が含まれます。

`wcsrchr` 関数と `_mbsrchr` 関数は、 `strrchr`関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcsrchr` 関数の引数と戻り値はワイド文字列で、`_mbsrchr` 関数の引数と戻り値はマルチバイト文字列です。

C では、これらの関数は、最初の引数の**定数**ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 **Const**へのポインターを受け取るオーバーロードは、 **const**へのポインターを返します。非**const**へのポインターを受け取るバージョンは、非**const**へのポインターを返します。 これらの関数の**const**と**const**以外の両方のバージョンが使用できる場合、マクロ _CRT_CONST_CORRECT_OVERLOADS が定義されます。 両方の C++ オーバーロードに非**定数**の動作が必要な場合は、シンボル _CONST_RETURN を定義します。

`_mbsrchr` はそのパラメーターを検証します。 *Str*が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可され`errno`た場合、は EINVAL `_mbsrchr`に設定され、0を返します。 `strrchr` および `wcsrchr` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。

出力値は、ロケールの LC_CTYPE カテゴリの設定に影響されます。詳細については、「 [setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsrchr`|`strrchr`|`_mbsrchr`|`wcsrchr`|
|**該当なし**|**該当なし**|`_mbsrchr_l`|**該当なし**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|`strrchr`|\<string.h>|
|`wcsrchr`|\<string.h> または \<wchar.h>|
|`_mbsrchr`, `_mbsrchr_l`|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

`strrchr` の使用例については、「[strchr](strchr-wcschr-mbschr-mbschr-l.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strchr、wcschr、_mbschr、_mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
