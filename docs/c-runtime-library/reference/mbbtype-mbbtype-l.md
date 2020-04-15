---
title: _mbbtype、_mbbtype_l
ms.date: 4/2/2020
api_name:
- _mbbtype
- _mbbtype_l
- _o__mbbtype
- _o__mbbtype_l
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
ms.openlocfilehash: 7e2e818ed70ec393e4f81008f76ca9efe9cfa7e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341410"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype、_mbbtype_l

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

*C*<br/>
テスト対象の文字。

*type*<br/>
テストするバイトの種類。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbbtype**文字列のバイトの型を返します。 この決定は、コントロールテスト条件を提供する*type*の値で指定された状況依存です。 *type*は、文字列内の前のバイトの型です。 次の表のマニフェスト定数は、Mbctype.h で定義されています。

|*型*の値|**_mbbtype**テスト|戻り値|*C*|
|---------------------|--------------------------|------------------|---------|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_SINGLE** (0)|1 バイト (0x20 - 0x7E、0xA1 - 0xDF)|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_LEAD** (1)|マルチバイト文字の先頭バイト (0x81 - 0x9F、0xE0 - 0xFC)|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_ILLEGAL**<br /><br /> ( -1)|無効な文字 (0x20 - 0x7E,0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC を除く任意の値|
|1|有効な末尾バイト|**_MBC_TRAIL** (2)|マルチバイト文字の末尾バイト (0x40 - 0x7E、 0x80 - 0xFC)|
|1|有効な末尾バイト|**_MBC_ILLEGAL**<br /><br /> ( -1)|無効な文字 (0x20 - 0x7E,0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC を除く任意の値|

## <a name="remarks"></a>解説

**_mbbtype**関数は、マルチバイト文字のバイトの型を決定します。 *型*の値が 1 を除く任意の値である場合 **、_mbbtypeは**、マルチバイト文字の有効な 1 バイトまたは先頭バイトをテストします。 *型*の値が 1 の場合 **、_mbbtype**はマルチバイト文字の有効な後部バイトをテストします。

出力値は、ロケールの**LC_CTYPE**カテゴリ設定の設定によって影響されます。詳細については[、setlocale を参照_wsetlocale。](setlocale-wsetlocale.md) この関数の **_mbbtype**バージョンでは、このロケールに依存する動作に現在のロケールが使用されます。**_mbbtype_l**バージョンは、代わりに渡されたロケールパラメータを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンでは **、_mbbtype**は**chkctype**という名前でした。 新しいコードの場合は、代わりに **_mbbtype**を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 戻り値として使用されるマニフェスト定数の定義。

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
