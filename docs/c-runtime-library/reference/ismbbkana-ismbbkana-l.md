---
title: _ismbbkana、_ismbbkana_l
ms.date: 11/04/2016
apiname:
- _ismbbkana_l
- _ismbbkana
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
- _ismbbkana_l
- ismbbkana_l
- ismbbkana
- _ismbbkana
helpviewer_keywords:
- _ismbbkana_l function
- _ismbbkana function
- ismbbkana function
- ismbbkana_l function
ms.assetid: 64d4eb4a-205a-40ef-be35-ff9d77fabbaf
ms.openlocfilehash: 723b914f5df92f20e4982bf6f7f04d1b251606f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287018"
---
# <a name="ismbbkana-ismbbkanal"></a>_ismbbkana、_ismbbkana_l

カタカナ シンボルのテスト。コード ページ 932 固有のテストです。

## <a name="syntax"></a>構文

```C
int _ismbbkana(
   unsigned int c
);
int _ismbbkana_l(
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

**_ismbbkana**場合は、0 以外の値を返します、整数*c*でない場合は 0 またはカタカナ シンボルのです。 **_ismbbkana**ロケールに依存する文字については、現在のロケールを使用します。 **_ismbbkana_l**で渡されたロケール オブジェクトを使用すると同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_ismbbkana**|\<mbctype.h>|
|**_ismbbkana_l**|\<mbctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
