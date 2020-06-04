---
title: _get_terminate
ms.date: 4/2/2020
api_name:
- _get_terminate
- _o__get_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_terminate
- _get_terminate
- __get_terminate
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
ms.openlocfilehash: 2ee68506437cb1c5b76cac05d674527095055055
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920409"
---
# <a name="_get_terminate"></a>_get_terminate

**Terminate**によって呼び出される終了ルーチンを返します。

## <a name="syntax"></a>構文

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>戻り値

[set_terminate](set-terminate-crt.md) で登録されている関数へのポインターを返します。 関数が設定されていない場合は、戻り値を使用して既定の動作を復元できます。この値は**NULL**でもかまいません。

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[取り消し](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[解約](terminate-crt.md)<br/>
[不適切](unexpected-crt.md)<br/>
