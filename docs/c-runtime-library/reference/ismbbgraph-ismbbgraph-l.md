---
title: _ismbbgraph、_ismbbgraph_l
ms.date: 4/2/2020
api_name:
- _ismbbgraph_l
- _ismbbgraph
- _o__ismbbgraph
- _o__ismbbgraph_l
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
- _ismbbgraph
- _ismbbgraph_l
- ismbbgraph
- ismbbgraph_l
helpviewer_keywords:
- _ismbbgraph_l function
- ismbbgraph_l function
- _ismbbgraph function
- ismbbgraph function
ms.assetid: b60db718-134f-4796-acc1-592d0b9efbb7
ms.openlocfilehash: 60b8a974ab27878a379e3a9ad2596a23ed31757f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909505"
---
# <a name="_ismbbgraph-_ismbbgraph_l"></a>_ismbbgraph、_ismbbgraph_l

特定のマルチバイト文字がグラフィカルな文字かどうかを判定します。

## <a name="syntax"></a>構文

```C
int _ismbbgraph (
   unsigned int c
);
int _ismbbgraph_l (
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*40u-c*<br/>
テストする整数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

式が以下の場合は、0 以外の値を返します。

`isctype(c, ( _PUNCT | _UPPER | _LOWER | _DIGIT )) || _ismbbkprint(c)`

*c*の場合は0以外の。それ以外の場合は0。 **_ismbbgraph**は、ロケールに依存する動作に現在のロケールを使用します。 **_ismbbgraph_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbbgraph**|\<mbctype.h>|
|**_ismbbgraph_l**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
