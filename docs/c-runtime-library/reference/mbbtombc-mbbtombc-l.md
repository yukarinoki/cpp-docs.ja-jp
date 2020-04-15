---
title: _mbbtombc、_mbbtombc_l
ms.date: 4/2/2020
api_name:
- _mbbtombc_l
- _mbbtombc
- _o__mbbtombc
- _o__mbbtombc_l
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
ms.openlocfilehash: 5d26b06da1dcf8c53abda5d4ff2ee06ec3e7cd11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341426"
---
# <a name="_mbbtombc-_mbbtombc_l"></a>_mbbtombc、_mbbtombc_l

1 バイトのマルチバイト文字を、対応する 2 バイトのマルチバイト文字に変換します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned int _mbbtombc(
   unsigned int c
);
unsigned int _mbbtombc_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
変換する 1 バイト文字。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbbtombc**が c を変換すると *、* マルチバイト文字が返されます。それ以外の場合は*c*を返します。

## <a name="remarks"></a>解説

**_mbbtombc**関数は、指定された 1 バイトマルチバイト文字を対応する 2 バイトマルチバイト文字に変換します。 変換する文字は、0x20 から 0x7E または 0xA1 から 0xDF の範囲内になければなりません。

出力値は、ロケールの**LC_CTYPE**カテゴリ設定の設定によって影響されます。詳細については[、setlocale を参照_wsetlocale。](setlocale-wsetlocale.md) この関数のバージョンは同じですが **、_mbbtombc**は現在のロケールをこのロケールに依存する動作に使用し、代わりに渡されたロケール パラメーターを使用 **_mbbtombc_l**点を除きます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンでは **、_mbbtombc**は **「半禅**」と名付けられました。 新しいコードの場合は **、_mbbtombc**を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbbtombc**|\<mbstring.h>|
|**_mbbtombc_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb、_mbctombb_l](mbctombb-mbctombb-l.md)<br/>
