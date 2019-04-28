---
title: _ismbbkpunct、_ismbbkpunct_l
ms.date: 11/04/2016
apiname:
- _ismbbkpunct_l
- _ismbbkpunct
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
ms.openlocfilehash: 24a82bdf0dde2beb0978226208c151689e06ed72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287031"
---
# <a name="ismbbkpunct-ismbbkpunctl"></a>_ismbbkpunct、_ismbbkpunct_l

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

*c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_ismbbkpunct**場合は、0 以外の値を返します、整数*c*は非 ASCII 区切り記号、または 0 でない場合。 たとえば、コード ページ 932 でのみ **_ismbbkpunct** は、カタカナ区切り文字をテストします。 **_ismbbkpunct**任意のロケールに依存する文字設定に現在のロケールを使用します。 **_ismbbkpunct_l**で渡されるロケールを使用すると同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_ismbbkpunct**|\<mbctype.h>|
|**_ismbbkpunct_l**|\<mbctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
