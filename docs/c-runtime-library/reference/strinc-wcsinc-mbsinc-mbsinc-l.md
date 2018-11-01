---
title: _strinc、_wcsinc、_mbsinc、_mbsinc_l
ms.date: 11/04/2016
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
ms.openlocfilehash: 1f23f57582d9f65ca728beac2c83804dff9935a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612902"
---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc、_wcsinc、_mbsinc、_mbsinc_l

文字列ポインターを 1 文字進めます。

> [!IMPORTANT]
> **_mbsinc**と **_mbsinc_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *_strinc(
   const char *current,
   _locale_t locale
);
wchar_t *_wcsinc(
   const wchar_t *current,
   _locale_t locale
);
unsigned char *_mbsinc(
   const unsigned char *current
);
unsigned char *_mbsinc_l(
   const unsigned char *current,
   _locale_t locale
);

```

### <a name="parameters"></a>パラメーター

*current*<br/>
文字ポインター。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチン直後に続く文字へのポインターを返します*現在*します。

## <a name="remarks"></a>Remarks

**_Mbsinc**直後に続くマルチバイト文字の最初のバイトへのポインターを返します関数*現在*します。 **_mbsinc**に従ってマルチバイト文字シーケンスを認識、[マルチバイト コード ページ](../../c-runtime-library/code-pages.md)は、現在使用中です。**_mbsinc_l**で渡されるロケール パラメーターを代わりに使用すると同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

汎用テキスト関数 **_tcsinc**にマップ、Tchar.h で定義されている、 **_mbsinc**場合 **_MBCS**が定義されている、または **_wcsinc**場合 **_UNICODE**は定義されています。 それ以外の場合、 **_tcsinc**マップ **_strinc**します。 **_strinc**と **_wcsinc**の 1 バイト文字とワイド文字バージョン **_mbsinc**します。 **_strinc**と **_wcsinc**このマッピングにのみ提供され、それ以外の場合は使用できません。 詳細については、「[Using Generic-Text Mappings](../../c-runtime-library/using-generic-text-mappings.md)」(汎用テキスト マップの使用) および「[Generic-Text Mappings](../../c-runtime-library/generic-text-mappings.md)」(汎用テキスト マップ) をご覧ください。

場合*現在*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**EINVAL**設定と**errno**に**EINVAL**します。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbsinc**|\<mbstring.h>|
|**_mbsinc_l**|\<mbstring.h>|
|**_strinc**|\<tchar.h>|
|**_wcsinc**|\<tchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdec、_wcsdec、_mbsdec、_mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strnextc、_wcsnextc、_mbsnextc、_mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc、_wcsninc、_mbsninc、_mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
