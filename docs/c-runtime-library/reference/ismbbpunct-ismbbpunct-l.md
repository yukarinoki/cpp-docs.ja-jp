---
title: _ismbbpunct、_ismbbpunct_l
ms.date: 4/2/2020
api_name:
- _ismbbpunct
- _ismbbpunct_l
- _o__ismbbpunct
- _o__ismbbpunct_l
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
- ismbbpunct
- ismbbpunct_l
- _ismbbpunct_l
- _ismbbpunct
helpviewer_keywords:
- ismbbpunct function
- _ismbbpunct function
- ismbbpunct_l function
- _ismbbpunct_l function
ms.assetid: 1976c9d3-7d1a-415f-ac52-2715c7bb56eb
ms.openlocfilehash: db0725215b6568300602c55ca253d959c27aedc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343463"
---
# <a name="_ismbbpunct-_ismbbpunct_l"></a>_ismbbpunct、_ismbbpunct_l

特定の文字が区切り文字かどうかを判断します。

## <a name="syntax"></a>構文

```C
int _ismbbpunct(
   unsigned int c
);
int _ismbbpunct_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
テストする整数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_ismbbpunct**は、整数*c*が非 ASCII 句読点記号の場合、0 以外の値を返します。 **_ismbbpunct**は、ロケールに依存する文字設定に現在のロケールを使用します。 **_ismbbpunct_l**は、渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbbpunct**|\<mbctype.h>|
|**_ismbbpunct_l**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbbルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
