---
title: btowc
ms.date: 4/2/2020
api_name:
- btowc
- _o_btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- btowc
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: cbeff70674a257217c66d39475a2c809c9bd9559
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913364"
---
# <a name="btowc"></a>btowc

初回のシフト状態で整数が有効なシングルバイト文字を表すかどうかを判断します。

## <a name="syntax"></a>構文

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>パラメーター

*記号*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

初回のシフト状態で整数が有効なシングルバイト文字を表す場合、文字のワイド文字表現を返します。 初回のシフト状態で整数が EOF の場合、あるいは有効なシングルバイト文字ではない場合、WEOF を返します。 この関数の出力は、現在の**LC_TYPE**ロケールによって影響を受けます。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**btowc**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
