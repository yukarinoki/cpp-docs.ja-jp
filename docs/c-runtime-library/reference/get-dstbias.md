---
title: _get_dstbias | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82e334c6fcb282bebb003992219f6cf215ab7437
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397767"
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

正常終了した場合や、0 **errno**値の場合は、エラーが発生します。

## <a name="remarks"></a>コメント

**_Get_dstbias**関数は、整数としての夏時間の秒数を取得します。 夏時間が適用されている場合、既定のオフセットは 3,600 秒であり、これは 1 時間の秒数です (ただし、一部の地域は 2 時間のオフセットを実施しています)。

場合*秒*は**NULL**、」の説明に従って、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**EINVAL**です。

マクロではなくこの関数を使用することをお勧め **_dstbias**非推奨の関数または **__dstbias**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
