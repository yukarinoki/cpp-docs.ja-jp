---
title: _mbbtype、_mbbtype_l
ms.date: 11/04/2016
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
ms.openlocfilehash: a6d17b99e4314c2ab836a16129ab8a0e6ac7720e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467172"
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype、_mbbtype_l

前のバイトに基づいて、バイトの種類を返します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テスト対象の文字。

*type*<br/>
テストするバイトの種類。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbbtype**文字列内のバイトの種類を返します。 この決定は、の値で指定されたキーによる状況依存*型*コントロールのテスト条件を提供します。 *型*文字列の前のバイトの種類です。 次の表のマニフェスト定数は、Mbctype.h で定義されています。

|値*型*|**_mbbtype**のテスト|戻り値|*c*|
|---------------------|--------------------------|------------------|---------|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_SINGLE** (0)|1 バイト (0x20 - 0x7E、0xA1 - 0 xdf)|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_LEAD** (1)|マルチバイト文字の先行バイト (0x81 - 0x9F、0xE0 - 0 xfc)|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**継続**<br /><br /> ( -1)|無効な文字 (すべて以外の値 0x20 - 0x7E、0xA1 - 0 xdf、0x81 - 0x9F、0xE0 - 0 xfc|
|1|有効な末尾バイト|**_MBC_TRAIL** (2)|マルチバイト文字の後続バイト (0x40 ~ 0x7E、0x80 ~ 0 xfc)|
|1|有効な末尾バイト|**継続**<br /><br /> ( -1)|無効な文字 (すべて以外の値 0x20 - 0x7E、0xA1 - 0 xdf、0x81 - 0x9F、0xE0 - 0 xfc|

## <a name="remarks"></a>Remarks

**_Mbbtype**関数は、マルチバイト文字のバイトの種類を決定します。 場合の値*型*1 以外の値は、 **_mbbtype**マルチバイト文字の有効な 1 バイトまたは先頭バイトをテストします。 場合の値*型*は 1 です。 **_mbbtype**マルチバイト文字の有効な末尾バイトをテストします。

出力値の設定に影響は、 **LC_CTYPE**ロケールのカテゴリの設定; を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 **_Mbbtype**この関数のバージョンは、このロケールに依存する動作の現在のロケールを使用、 **_mbbtype_l**バージョンは、代わりに渡されるロケール パラメーターを使用する点を除いて同じです. 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンで **_mbbtype**という名前が**chkctype**します。 新しいコードを使用して **_mbbtype**代わりにします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 戻り値として使用されるマニフェスト定数の定義。

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
