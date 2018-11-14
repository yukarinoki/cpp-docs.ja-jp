---
title: _set_doserrno
ms.date: 11/04/2016
apiname:
- _set_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_doserrno
- set_doserrno
helpviewer_keywords:
- _set_doserrno function
- doserrno global variable
- set_doserrno function
- _doserrno global variable
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
ms.openlocfilehash: 98b43c908a7ee48a89158c987fe64420f6639a79
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327786"
---
# <a name="setdoserrno"></a>_set_doserrno

[_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) グローバル変数の値を設定します。

## <a name="syntax"></a>構文

```C
errno_t _set_doserrno( int error_value );
```

### <a name="parameters"></a>パラメーター

*error_value*<br/>
新しい値 **_doserrno**します。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。

## <a name="remarks"></a>Remarks

使用できる値は Errno.h で定義します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_set_doserrno**|\<stdlib.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_get_doserrno](get-doserrno.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
