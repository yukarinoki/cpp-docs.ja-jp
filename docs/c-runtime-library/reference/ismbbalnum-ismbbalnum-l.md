---
title: _ismbbalnum、_ismbbalnum_l
ms.date: 4/2/2020
api_name:
- _ismbbalnum
- _ismbbalnum_l
- _o__ismbbalnum
- _o__ismbbalnum_l
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
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
ms.openlocfilehash: abbc664170c274929875ef2e4b7af70bc5812a94
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917553"
---
# <a name="_ismbbalnum-_ismbbalnum_l"></a>_ismbbalnum、_ismbbalnum_l

指定されたマルチバイト文字が英字または数字かどうかを判定します。

## <a name="syntax"></a>構文

```C
int _ismbbalnum(
   unsigned int c
);
int _ismbbalnum_l(
   unsigned int c
);
```

### <a name="parameters"></a>パラメーター

*40u-c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

次の式の場合、 **_ismbbalnum**は0以外の値を返します。

`isalnum(c) || _ismbbkalnum(c)`

*c*の場合は0以外の。それ以外の場合は0。

**_L**サフィックスが付いたこの関数のバージョンは、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用する点を除いて同じです。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbbalnum**|\<mbctype.h>|
|**_ismbbalnum_l**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
