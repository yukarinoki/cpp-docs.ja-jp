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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: dca59f2d31cc5ad843a48e9825ef6a617d46ae4a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919587"
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

*40u-c*<br/>
テスト対象の文字。

*type*<br/>
テストするバイトの種類。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbbtype**は、文字列内のバイトの型を返します。 この決定は、コントロールのテスト条件を提供する*型*の値によって指定された、状況に依存します。 *type*は、文字列内の前のバイトの型です。 次の表のマニフェスト定数は、Mbctype.h で定義されています。

|*型*の値|テストの **_mbbtype**|戻り値|*40u-c*|
|---------------------|--------------------------|------------------|---------|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_SINGLE** (0)|1バイト (0x20-0x7E、0xA1-0xDF)|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_LEAD** (1)|マルチバイト文字の先頭バイト (0x81-0x9F、0xE0-0xFC)|
|1 以外の値|有効な 1 バイトまたは先頭バイト|**_MBC_ILLEGAL**<br /><br /> (-1)|無効な文字 (0x20-0x7E、0xA1-0xDF、0x81-0x9F、0xE0-0xFC を除く)|
|1|有効な末尾バイト|**_MBC_TRAIL** (2)|マルチバイト文字の末尾バイト (0x40-0x7E、0x80-0xFC)|
|1|有効な末尾バイト|**_MBC_ILLEGAL**<br /><br /> (-1)|無効な文字 (0x20-0x7E、0xA1-0xDF、0x81-0x9F、0xE0-0xFC を除く)|

## <a name="remarks"></a>解説

**_Mbbtype**関数は、マルチバイト文字のバイトの型を決定します。 *Type*の値が1以外の任意の値の場合、 **_mbbtype**は、有効な1バイト文字か、マルチバイト文字の先頭バイトかをテストします。 *型*の値が1の場合、 **_mbbtype**は、マルチバイト文字の有効な末尾バイトをテストします。

出力値は、ロケールの**LC_CTYPE**カテゴリの設定に影響されます。詳細について[は、「setlocale、_wsetlocale](setlocale-wsetlocale.md) 」を参照してください。 この関数の **_mbbtype**バージョンは、このロケールに依存する動作に現在のロケールを使用します。**_mbbtype_l**のバージョンは、渡されたロケールパラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

以前のバージョンでは、 **_mbbtype**には**chkctype**という名前が付けられていました。 新しいコードの場合は、代わりに **_mbbtype**を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 戻り値として使用されるマニフェスト定数の定義。

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
