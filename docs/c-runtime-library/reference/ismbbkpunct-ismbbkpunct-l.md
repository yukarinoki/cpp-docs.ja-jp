---
title: _ismbbkpunct、_ismbbkpunct_l
ms.date: 4/2/2020
api_name:
- _ismbbkpunct_l
- _ismbbkpunct
- _o__ismbbkpunct
- _o__ismbbkpunct_l
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
- ismbbkpunct_l
- _ismbbkpunct_l
- ismbbkpunct
- _ismbbkpunct
helpviewer_keywords:
- _ismbbkpunct_l function
- ismbbkpunct_l function
- ismbbkpunct function
- _ismbbkpunct function
ms.assetid: a04c59cd-5ca7-4296-bec0-2b0d7f04edd0
ms.openlocfilehash: 24e1676422d913bf406fc4cb5f114c1c025bdb97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343589"
---
# <a name="_ismbbkpunct-_ismbbkpunct_l"></a>_ismbbkpunct、_ismbbkpunct_l

マルチバイト文字が区切り文字かどうかをチェックします。

## <a name="syntax"></a>構文

```C
int _ismbbkpunct(
   unsigned int c
);
int _ismbbkpunct_l(
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

**_ismbbkpunct**は、整数*c*が非 ASCII 句読点記号の場合は 0 以外の値を返し、非 ASCII 句読点シンボルの場合は 0 を返します。 たとえば、コード ページ 932 でのみ **_ismbbkpunct** は、カタカナ区切り文字をテストします。 **_ismbbkpunct**は、ロケールに依存する文字設定に現在のロケールを使用します。 **_ismbbkpunct_l**は、渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbbkpunct**|\<mbctype.h>|
|**_ismbbkpunct_l**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbbルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
