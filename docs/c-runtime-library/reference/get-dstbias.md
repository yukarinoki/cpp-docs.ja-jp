---
title: _get_dstbias
ms.date: 11/04/2016
apiname:
- _get_dstbias
- __dstbias
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __dstbias
- _get_dstbias
- get_dstbias
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
ms.openlocfilehash: 61807f854dc9c2f7de6f0acd5bbf4668987ce49e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579105"
---
# <a name="getdstbias"></a>_get_dstbias

夏時間のオフセット (秒単位) を取得します。

## <a name="syntax"></a>構文

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>パラメーター

*seconds*<br/>
夏時間のオフセット (秒単位)。

## <a name="return-value"></a>戻り値

成功した場合や、0 **errno**エラーが発生した場合の値します。

## <a name="remarks"></a>Remarks

**_Get_dstbias**関数は、整数としての夏時間の秒数を取得します。 夏時間が適用されている場合、既定のオフセットは 3,600 秒であり、これは 1 時間の秒数です (ただし、一部の地域は 2 時間のオフセットを実施しています)。

場合*秒*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**返します**EINVAL**します。

マクロの代わりにこの関数を使用することをお勧めします。 **_dstbias**または非推奨の関数 **__dstbias**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
