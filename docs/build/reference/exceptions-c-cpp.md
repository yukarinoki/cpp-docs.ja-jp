---
description: '詳細情報: 遅延読み込みの例外 (C/c + +)'
title: DLL 遅延読み込みの例外コード
ms.date: 01/19/2021
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.openlocfilehash: 214d8514baba7b180b8d838af8a6b6c0543cc1ce
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667184"
---
# <a name="dll-delay-load-exception-codes"></a>DLL 遅延読み込みの例外コード

エラーが発生すると、次の2つの構造化例外コードが発生する可能性があります。

- エラーの場合 `LoadLibrary`

- エラーの場合 `GetProcAddress`

例外情報マクロは次のようになります。

```C
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

スローされる例外コードは、 `VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND)` 標準 `VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)` 値と値です。 例外は、 `DelayLoadInfo` によって取得できる値の構造体へのポインターを、 `LPDWORD` `GetExceptionInformation` [`EXCEPTION_RECORD`](/windows/win32/api/winnt/ns-winnt-exception_record) 構造体のフィールドに渡し `ExceptionInformation[0]` ます。

また、フィールドに正しくないビットが設定されている場合は、 `grAttrs` 例外 `ERROR_INVALID_PARAMETER` がスローされます。 この例外は、すべてのインテントと目的で致命的です。

詳細については、「 [構造体と定数の定義](structure-and-constant-definitions.md)」を参照してください。

## <a name="see-also"></a>こちらもご覧ください

[エラー処理と通知](error-handling-and-notification.md)
