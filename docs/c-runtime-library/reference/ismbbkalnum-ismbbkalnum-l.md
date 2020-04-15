---
title: _ismbbkalnum、_ismbbkalnum_l
ms.date: 4/2/2020
api_name:
- _ismbbkalnum
- _ismbbkalnum_l
- _o__ismbbkalnum
- _o__ismbbkalnum_l
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
- _ismbbkalnum
- ismbbkalnum
- ismbbkalnum_l
- _ismbbkalnum_l
helpviewer_keywords:
- _ismbbkalnum_l function
- ismbbkalnum_l function
- _ismbbkalnum function
- ismbbkalnum function
ms.assetid: e1d70e7b-29d0-469c-9d93-442b99de22ac
ms.openlocfilehash: 936a7708a824ac6e9e8a07b34bbdb9a3b9e761ff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343673"
---
# <a name="_ismbbkalnum-_ismbbkalnum_l"></a>_ismbbkalnum、_ismbbkalnum_l

特定のマルチバイト文字が非 ASCII テキストの記号かどうかを判定します。

## <a name="syntax"></a>構文

```C
int _ismbbkalnum(
   unsigned int c
);
int _ismbbkalnum_l(
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

**_ismbbkalnum**は、整数*c*が句読点以外の ASCII 以外のテキスト シンボルの場合は 0 以外の値を返し、非 ASCII の場合は 0 を返します。 **_ismbbkalnum**は、ロケール依存の文字情報に現行ロケールを使用します。 **_ismbbkalnum_l**は、ロケールをパラメーターとして受け取る点を除いて **、_ismbbkalnum**と同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbbkalnum**|\<mbctype.h>|
|**_ismbbkalnum_l**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbbルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
