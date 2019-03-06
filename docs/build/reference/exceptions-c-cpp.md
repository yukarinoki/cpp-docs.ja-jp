---
title: 例外 (C/C++)
ms.date: 11/04/2016
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
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
ms.openlocfilehash: 9c86d99b365994870b991967b6cab6e6ee5c5088
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422989"
---
# <a name="exceptions-cc"></a>例外 (C/C++)

2 つの例外コードは、エラーが発生したときに発生することができます。

- **LoadLibrary**エラー

- **GetProcAddress**エラー

例外情報を次に示します。

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

スローされた例外コードは、標準の VcppException (ERROR_SEVERITY_ERROR、ERROR_MOD_NOT_FOUND) と VcppException (ERROR_SEVERITY_ERROR、ERROR_PROC_NOT_FOUND) 値です。 例外へのポインターを渡す、 **DelayLoadInfo** LPDWORD 値を取得できる構造**GetExceptionInformation**で、 [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record)構造体、ExceptionInformation [0] のフィールド。

さらに、不適切なビットを grAttrs フィールドに設定されている場合、例外が試行がスローされます。 この例外を消して、致命的です。

参照してください[構造体と定数定義](../../build/reference/structure-and-constant-definitions.md)詳細についてはします。

## <a name="see-also"></a>関連項目

[エラー処理と通知](../../build/reference/error-handling-and-notification.md)
