---
description: '詳細については、次を参照してください: _get_unexpected'
title: _get_unexpected
ms.date: 1/14/2021
api_name:
- _get_unexpected
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __get_unexpected
- _get_unexpected
- get_unexpected
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
ms.openlocfilehash: fb23aa9eee66a4ed981e5575e5a36ad4bbb39f84
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242619"
---
# `_get_unexpected`

によって呼び出される終了ルーチンを返し **`unexpected`** ます。

## <a name="syntax"></a>構文

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>戻り値

によって登録された関数へのポインターを返し [`set_unexpected`](set-unexpected-crt.md) ます。 関数が設定されていない場合は、戻り値を使用して既定の動作を復元できます。この値はでもかまい **`NULL`** ません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`_get_unexpected`**|\<eh.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>参照

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[`abort`](abort.md)<br/>
[`set_terminate`](set-terminate-crt.md)<br/>
[`terminate`](terminate-crt.md)<br/>
[`unexpected`](unexpected-crt.md)<br/>
