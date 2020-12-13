---
description: '詳細については、次を参照してください: _get_timezone'
title: _get_timezone
ms.date: 4/2/2020
api_name:
- _get_timezone
- _o__get_timezone
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_timezone
- get_timezone
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
ms.openlocfilehash: 9fb42603d0b7d63cbbb18c4904c221cd2edeb0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338972"
---
# <a name="_get_timezone"></a>_get_timezone

協定世界時刻 (UTC) と現地時刻の秒単位の差を取得します。

## <a name="syntax"></a>構文

```C
error_t _get_timezone(
    long* seconds
);
```

### <a name="parameters"></a>パラメーター

*seconds*<br/>
UTC と現地時刻の秒単位の差。

## <a name="return-value"></a>戻り値

成功した場合は0、エラーが発生した場合は **errno** 値。

## <a name="remarks"></a>解説

**_Get_timezone** 関数は、UTC と現地時刻の間の差を整数として取得します。 既定値は、太平洋標準時 (UTC から 8 時間遅れ) を表す 28,800 秒です。

*Seconds* が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は **errno** を **einval** に設定し、 **einval** を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_timezone**|\<time.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_tzname](get-tzname.md)<br/>
