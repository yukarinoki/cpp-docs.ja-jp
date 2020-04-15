---
title: _ismbblead、_ismbblead_l
description: Microsoft C ランタイム ライブラリ (CRT) _ismbbleadおよび_ismbblead_l関数について説明します。
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: ee3085d49a27f2f3c97c6578463cf3a0598b73c7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343577"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead、_ismbblead_l

マルチバイト文字の先頭バイトかどうかを判別するために、文字をテストします。

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

*C*\
テストする整数。

*ロケール*\
使用するロケール。

## <a name="return-value"></a>戻り値

整数*c*がマルチバイト文字の最初のバイトの場合は、0 以外の値を返します。

## <a name="remarks"></a>解説

マルチバイト文字は、先行バイトとそれに続く後続バイトで構成されます。 先行バイトは、特定の文字セットの特定の範囲内にあるかどうかで識別されます。 たとえば、コード ページ 932 の場合のみ、リード バイトの範囲は 0x81 から 0x9F、0xE0 から 0xFC までです。

**_ismbblead**は、ロケールに依存する動作に現在のロケールを使用します。 **_ismbblead_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

ロケールが UTF-8 の場合 **、_ismbblead_ismbblead_l、c**がリードバイト*c*かどうかに関係**なく、常**に 0 (false) を返します。

**_ismbblead**と **_ismbblead_l**は、標準 C ライブラリの一部ではなく、マイクロソフト固有のものです。 移植可能なコードを使用する場所で使用することはお勧めしません。 標準 C 互換性のために、代わりに**mbrlen を**使用してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト・ルーチン・マッピング

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
[_ismbbルーチン](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
