---
title: _mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l
ms.date: 4/2/2020
api_name:
- _mbctolower_l
- _mbctoupper_l
- _mbctoupper
- _mbctolower
- _o__mbctolower
- _o__mbctolower_l
- _o__mbctoupper
- _o__mbctoupper_l
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
- mbctoupper_l
- mbctolower_l
- _mbctolower
- _mbctolower_l
- _mbctoupper
- mbctoupper
- mbctolower
- _mbctoupper_l
helpviewer_keywords:
- _mbctolower function
- mbctolower_l function
- totupper function
- _mbctoupper function
- totlower function
- _mbctoupper_l function
- mbctolower function
- _totupper function
- _mbctolower_l function
- mbctoupper_l function
- _totlower function
- mbctoupper function
ms.assetid: 787fab71-3224-4ed7-bc93-4dcd8023fc54
ms.openlocfilehash: 49915a4017040200afca950cee5e1ac31184c589
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341059"
---
# <a name="_mbctolower-_mbctolower_l-_mbctoupper-_mbctoupper_l"></a>_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l

マルチバイト文字が大文字か小文字かをテストして変換します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned int _mbctolower(
   unsigned int c
);
unsigned int _mbctolower_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbctoupper(
   unsigned int c
);
unsigned int _mbctoupper_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
変換するマルチバイト文字。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの関数は、変換された文字*c*を返します (可能な場合)。 それ以外の場合は、文字*c*を変更せずに返します。

## <a name="remarks"></a>解説

関数は文字*c*をテストし、可能であれば、次のいずれかの変換を適用します。

|ルーチン|変換|
|--------------|--------------|
|**_mbctolower**, **_mbctolower_l**|大文字を小文字に変換します。|
|**_mbctoupper**, **_mbctoupper_l**|小文字を大文字に変換します。|

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l**サフィックスを持たないこの関数のバージョンでは、このロケール依存の動作に現在のロケールが使用されます。**_l**サフィックスを持つバージョンは、代わりに渡されたロケールパラメータを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンでは **、_mbctolower** **jtolower**と呼ばれ **、_mbctoupper**は**jtoupper**と呼ばれます。 新しいコードでは、代わりに新しい名前を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_totlower**|**トローワー**|**_mbctolower**|**towlower**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_t**|
|**_totupper**|**Toupper**|**_mbctoupper**|**towupper**|
|**_totupper_l**|**toupper_l**|**_mbctoupper_l**|**_towupper_l**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|--------------|---------------------|
|**_mbctolower**, **_mbctolower_l**|\<mbstring.h>|
|**_mbctoupper**, **_mbctoupper_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[_mbbtombc、_mbbtombc_l](mbbtombc-mbbtombc-l.md)<br/>
[_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)<br/>
[_mbctombb、_mbctombb_l](mbctombb-mbctombb-l.md)<br/>
