---
title: _get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler
ms.date: 11/04/2016
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
ms.openlocfilehash: 7d1a87f9ade0845994918d5a4d59dc56e190d2b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623978"
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler

CRT が無効な引数を検出したときに呼び出される関数を取得します。

## <a name="syntax"></a>構文

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>戻り値

現在設定されている無効なパラメーター ハンドラー関数を指すポインター、または何も設定されていない場合は Null ポインターです。

## <a name="remarks"></a>Remarks

**_Get_invalid_parameter_handler**関数は、現在設定されている取得グローバルの無効なパラメーター ハンドラー。 無効なグローバル パラメーター ハンドラーが設定されていない場合は、Null ポインターを返します。 同様に、 **_get_thread_local_invalid_parameter_handler**ハンドラーが設定されていない場合、呼び出されたスレッドまたは null ポインターの現在のスレッド ローカルの無効なパラメーター ハンドラーを取得します。 グローバルとスレッド ローカルの無効なパラメーター ハンドラーを設定する方法については、「[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)」を参照してください。

返される無効なパラメーター ハンドラー関数ポインターには、次の型があります。

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

無効なパラメーター ハンドラーの詳細については、「[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)」内のプロトタイプを参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_invalid_parameter_handler**、 **_get_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> または \<stdlib.h>|

**_Get_invalid_parameter_handler**と **_get_thread_local_invalid_parameter_handler**関数は、Microsoft 固有の仕様。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[CRT 関数のセキュリティが強化されたバージョン](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
