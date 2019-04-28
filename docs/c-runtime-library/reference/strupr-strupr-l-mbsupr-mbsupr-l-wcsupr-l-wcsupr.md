---
title: _strupr、_strupr_l、_mbsupr、_mbsupr_l、_wcsupr_l、_wcsupr
ms.date: 11/04/2016
apiname:
- _mbsupr_l
- _mbsupr
- _strupr_l
- _wcsupr
- _wcsupr_l
- _strupr
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsupr
- _ftcsupr
- mbsupr
- _tcsupr
- strupr_l
- _fstrupr
- _strupr
- mbsupr_l
- _wcsupr
helpviewer_keywords:
- tcsupr_l function
- mbsupr function
- strupr function
- uppercase, converting strings to
- wcsupr function
- _wcsupr function
- string conversion [C++], case
- ftcsupr function
- _ftcsupr function
- _wcsupr_l function
- wcsupr_l function
- strings [C++], case
- tcsupr function
- _tcsupr_l function
- _fstrupr function
- _strupr_l function
- _mbsupr_l function
- converting case, CRT functions
- fstrupr function
- mbsupr_l function
- strupr_l function
- _strupr function
- _mbsupr function
- _tcsupr function
- strings [C++], converting case
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
ms.openlocfilehash: c3d155ebfdc40c5dd479cffed0b892dd73f80138
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269031"
---
# <a name="strupr-struprl-mbsupr-mbsuprl-wcsuprl-wcsupr"></a>_strupr、_strupr_l、_mbsupr、_mbsupr_l、_wcsupr_l、_wcsupr

文字列を大文字に変換します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[_strupr_s、_strupr_s_l、_mbsupr_s、_mbsupr_s_l、_wcsupr_s、_wcsupr_s_l](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)」をご覧ください。

> [!IMPORTANT]
> **_mbsupr**と **_mbsupr_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *_strupr(
   char *str
);
wchar_t *_wcsupr(
   wchar_t *str
);
unsigned char *_mbsupr(
   unsigned char *str
);
char *_strupr_l(
   char *str,
   _locale_t locale
);
wchar_t *_wcsupr_l(
   wchar_t *str,
   _locale_t locale
);
unsigned char *_mbsupr_l(
   unsigned char *str,
   _locale_t locale
);
template <size_t size>
char *_strupr(
   char (&str)[size]
); // C++ only
template <size_t size>
wchar_t *_wcsupr(
   wchar_t (&str)[size]
); // C++ only
template <size_t size>
unsigned char *_mbsupr(
   unsigned char (&str)[size]
); // C++ only
template <size_t size>
char *_strupr_l(
   char (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
wchar_t *_wcsupr_l(
   wchar_t (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbsupr_l(
   unsigned char (&str)[size],
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*str*<br/>
大文字にする文字列。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

変更された文字列へのポインターを返します。 同じ位置で変更が実行されるため、返されるポインターは入力引数として渡されるポインターと同じです。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>Remarks

**_Strupr**インプレースでの小文字の変換関数*str*を大文字にします。 変換がによって決定されます、 **LC_CTYPE**ロケールのカテゴリの設定。 他の文字は影響を受けません。 詳細については**LC_CTYPE**を参照してください[setlocale](setlocale-wsetlocale.md)します。 この関数のバージョン、 **_l**サフィックスを使用しているバージョンは、現在のロケール、 **_l**代わりに渡されたロケールを使用する点を除いて、サフィックスは同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**_wcsupr**と **_mbsupr**のワイド文字とマルチバイト文字バージョン **_strupr**します。 引数と戻り値 **_wcsupr**はワイド文字列 **_mbsupr**はマルチバイト文字の文字列。 それ以外では、これらの関数の動作は同じです。

場合*str* null ポインターの場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行が続行すると、これらの関数の戻り値、元の文字列とセットを許可された場合**errno**に**EINVAL**します。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsupr**|**_strupr**|**_mbsupr**|**_wcsupr**|
|**_tcsupr_l**|**_strupr_l**|**_mbsupr_l**|**_wcsupr_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_strupr**、 **_strupr_l**|\<string.h>|
|**_wcsupr**、 **_wcsupr_l**|\<string.h> または \<wchar.h>|
|**_mbsupr**、 **_mbsupr_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[_strlwr](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md) に関する記事の例をご覧ください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strlwr、_wcslwr、_mbslwr、_strlwr_l、_wcslwr_l、_mbslwr_l](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)<br/>
