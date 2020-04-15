---
title: _mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l
ms.date: 4/2/2020
api_name:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
- _o__mbcjistojms
- _o__mbcjistojms_l
- _o__mbcjmstojis
- _o__mbcjmstojis_l
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
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
ms.openlocfilehash: ef0010088543f1c580e536f120cae681a7582491
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341188"
---
# <a name="_mbcjistojms-_mbcjistojms_l-_mbcjmstojis-_mbcjmstojis_l"></a>_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l

日本工業標準 (JIS: Japan Industry Standard) 文字と Japan Microsoft (JMS) 文字の間を変換します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned int _mbcjistojms(
   unsigned int c
);
unsigned int _mbcjistojms_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbcjmstojis(
   unsigned int c
);
unsigned int _mbcjmstojis_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
変換する文字。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

日本語のロケールで、これらの関数は変換された文字を返すか、または変換可能でない場合は 0 を返します。 日本語以外のロケールで、これらの関数は、渡された文字を返します。

## <a name="remarks"></a>解説

**_mbcjistojms**関数は、日本工業規格 (JIS) 文字をマイクロソフトの漢字 (シフト JIS) 文字に変換します。 文字は、リードバイトとトレイルバイトが0x21から0x7Eの範囲内にある場合にのみ変換されます。 リードバイトまたはトライアルバイトがこの範囲外の場合 **、errno**は**EILSEQ**に設定されます。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

**_mbcjmstojis**関数は、シフト JIS 文字を JIS 文字に変換します。 文字は、先頭バイトが 0x81 から 0x9F または 0xE0 から 0xFC の範囲内にあり、その後のバイトが 0x40 - 0x7E または 0x80 - 0xFC の範囲にある場合にのみ変換されます。 その範囲の一部のコード ポイントには割り当てられた文字がないため、変換できないことに注意してください。

値*c*は、上位 8 ビットが変換する文字の先頭バイトを表し、下位 8 ビットが後部バイトを表す 16 ビット値である必要があります。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンでは **、_mbcjistojms**と **_mbcjmstojis**はそれぞれ**jistojms**と**jmstojis**と呼ばれました。 **_mbcjistojms**、 **_mbcjistojms_l**、 **_mbcjmstojis** 、および **_mbcjmstojis_l**を代わりに使用する必要があります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbcjistojms**|\<mbstring.h>|
|**_mbcjistojms_l**|\<mbstring.h>|
|**_mbcjmstojis**|\<mbstring.h>|
|**_mbcjmstojis_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[_ismbbルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
