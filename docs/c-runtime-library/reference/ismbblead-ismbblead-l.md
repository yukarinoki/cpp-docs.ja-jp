---
title: _ismbblead、_ismbblead_l
description: Microsoft C ランタイムライブラリ (CRT) の _ismbblead および _ismbblead_l 関数について説明します。
ms.date: 4/2/2020
api_name:
- _ismbblead_l
- _ismbblead
- _o__ismbblead
- _o__ismbblead_l
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
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: 7680793b71c4535ed75433ac98167e52a39896ba
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918665"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead、_ismbblead_l

文字をテストして、その文字がマルチバイト文字の先行バイトかどうかを判断します。

## <a name="syntax"></a>構文

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*40u-c*\
テストする整数。

*国*\
使用するロケール。

## <a name="return-value"></a>戻り値

は、整数*c*がマルチバイト文字の最初のバイトの場合、0以外の値を返します。

## <a name="remarks"></a>解説

マルチバイト文字は、先行バイトとそれに続く後続バイトで構成されます。 先行バイトは、特定の文字セットの特定の範囲内にあるかどうかで識別されます。 たとえば、コードページ932でのみ、潜在顧客のバイト範囲は 0x81-0x9F と 0xE0-0xFC です。

**_ismbblead**は、ロケールに依存する動作に現在のロケールを使用します。 **_ismbblead_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

ロケールが UTF-8 の場合、 **_ismbblead**と **_ismbblead_l**は常に 0 (false) を返します。これは、 *c*が先行バイトであるかどうかにかかわらず、常に返されます。

**_ismbblead**と **_Ismbblead_l**は、標準 C ライブラリの一部ではなく、Microsoft 固有のものです。 移植性のあるコードを作成する場合は、使用しないことをお勧めします。 標準 C 互換の場合は、代わりに**mbrlen**を使用してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキストルーチンのマッピング

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|常に false を返します|**_ismbblead**|常に false を返します|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|

\* テスト条件のマニフェスト定数の場合。

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)\
[_ismbb ルーチン](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
