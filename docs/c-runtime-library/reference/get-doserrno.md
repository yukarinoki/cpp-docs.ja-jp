---
description: '詳細については、次を参照してください: _get_doserrno'
title: _get_doserrno
ms.date: 4/2/2020
api_name:
- _get_doserrno
- _o__get_doserrno
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
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: ecd2dd79fa50cc8b723556399c7a637ce59e8461
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341465"
---
# <a name="_get_doserrno"></a>_get_doserrno

**Errno** 値に変換される前に、オペレーティングシステムによって返されたエラー値を取得します。

## <a name="syntax"></a>構文

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
**_Doserrno** グローバルマクロの現在の値が格納される整数へのポインター。

## <a name="return-value"></a>戻り値

**_Get_doserrno** が成功した場合は0を返します。失敗した場合は、エラーコードを返します。 *PValue* が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は **errno** を **einval** に設定し、 **einval** を返します。

## <a name="remarks"></a>解説

**_Doserrno** グローバルマクロは、プロセスの実行が開始される前に、CRT の初期化中に0に設定されます。 オペレーティング システム エラーを返すシステム レベルの関数呼び出しによって返されたオペレーティング システム エラー値に設定され、実行中に 0 にリセットされることはありません。 関数によって返されたエラー値をチェックするコードを記述する場合は、関数呼び出しの前に [_set_doserrno](set-doserrno.md)を使用して、常に **_doserrno** をクリアします。 別の関数呼び出しによって **_doserrno** が上書きされる可能性があるため、関数呼び出しの直後に **_get_doserrno** を使用して値を確認してください。

移植可能なエラーコードには、 **_get_doserrno** ではなく [_get_errno](get-errno.md)をお勧めします。

**_Doserrno** の使用可能な値は、で定義されてい \<errno.h> ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>、 \<cstdlib> (C++)|\<errno.h>、 \<cerrno> (C++)|

**_get_doserrno** は Microsoft の拡張機能です。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_set_doserrno](set-doserrno.md)<br/>
[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
