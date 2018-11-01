---
title: _mbctombb、_mbctombb_l
ms.date: 11/04/2016
apiname:
- _mbctombb_l
- _mbctombb
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
- _mbctombb_l
- _mbctombb
- mbctombb_l
- mbctombb
helpviewer_keywords:
- _mbctombb function
- mbctombb_l function
- mbctombb function
- _mbctombb_l function
ms.assetid: d90970b8-71ff-4586-b6a2-f9ceb811f776
ms.openlocfilehash: 7395d94a6ec18f989d4a7153425b7af406a0bf45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519835"
---
# <a name="mbctombb-mbctombbl"></a>_mbctombb、_mbctombb_l

2 バイト マルチバイト文字を、対応する 1 バイト マルチバイト文字に変換します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned int _mbctombb(
   unsigned int c
);
unsigned int _mbctombb_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
変換するマルチバイト文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

成功した場合、 **_mbctombb**と **_mbctombb_l**に対応する 1 バイト文字を返します*c*; 返します*c*.

## <a name="remarks"></a>Remarks

**_Mbctombb**と **_mbctombb_l**関数が特定のマルチバイト文字を対応する 1 バイト マルチバイト文字に変換します。 文字は 0 xdf に変換する範囲 0x20-0x7E または 0xA1 - 1 バイト文字に対応する必要があります。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 この関数のバージョン、 **_l**サフィックスは、このロケールに依存する動作の現在のロケールを使用とバージョン、 **_l**サフィックスは、渡されたロケール パラメーターを使用する点を除いて同じです代わりにします。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンで **_mbctombb**が呼び出された**zentohan**します。 使用 **_mbctombb**代わりにします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbctombb**|\<mbstring.h>|
|**_mbctombb_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[_mbbtombc、_mbbtombc_l](mbbtombc-mbbtombc-l.md)<br/>
[_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)<br/>
[_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l](mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)<br/>
