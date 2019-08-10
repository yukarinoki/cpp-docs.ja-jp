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
ms.openlocfilehash: cf38af464f08e143ed9073befe30f6aeb8b913b6
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915449"
---
# <a name="exceptions-cc"></a>例外 (C/C++)

エラーが発生すると、次の2つの例外コードが生成されます。

- **LoadLibrary**エラーの場合

- **GetProcAddress**エラーの場合

例外情報を次に示します。

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

スローされる例外コードは、標準の VcppException (ERROR_SEVERITY_ERROR、ERROR_MOD_NOT_FOUND) と VcppException (ERROR_SEVERITY_ERROR、ERROR_PROC_NOT_FOUND) の値です。 例外は、 [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-exception_record) Structure の exceptioninformation [0] フィールドの**getexceptioninformation**によって取得できる LPDWORD 値の**delayloadinfo**構造体へのポインターを渡します。

また、grAttrs フィールドで間違ったビットが設定されている場合は、例外 ERROR_INVALID_PARAMETER がスローされます。 この例外は、すべてのインテントと目的で致命的です。

詳細については[、「構造体と定数の定義](structure-and-constant-definitions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[エラー処理と通知](error-handling-and-notification.md)
