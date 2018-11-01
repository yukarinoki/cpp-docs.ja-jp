---
title: _mbbtombc、_mbbtombc_l
ms.date: 11/04/2016
apiname:
- _mbbtombc_l
- _mbbtombc
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
ms.openlocfilehash: 63b5dd33399201cd6ead7dbd1f710c8bebe53c69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547993"
---
# <a name="mbbtombc-mbbtombcl"></a>_mbbtombc、_mbbtombc_l

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

*c*<br/>
変換する 1 バイト文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

場合 **_mbbtombc**を正常に変換*c*、マルチバイト文字を返します。 それ以外を返します*c*します。

## <a name="remarks"></a>Remarks

**_Mbbtombc**関数は、特定の 1 バイト マルチバイト文字を対応する 2 バイト マルチバイト文字に変換します。 文字は、0x20-0x7E または 0xA1 - の範囲内で変換する 0 xdf にする必要があります。

出力値の設定に影響は、 **LC_CTYPE**ロケールのカテゴリの設定; を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 この関数のバージョンは同じですが、する点を除いて **_mbbtombc**このロケールに依存する動作に現在のロケールを使用し、 **_mbbtombc_l**で渡されるロケール パラメーターを代わりに使用します。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンで **_mbbtombc**という名前が**hantozen**します。 新しいコードを使用して **_mbbtombc**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbbtombc**|\<mbstring.h>|
|**_mbbtombc_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb、_mbctombb_l](mbctombb-mbctombb-l.md)<br/>
