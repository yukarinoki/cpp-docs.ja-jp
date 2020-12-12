---
description: '詳細については、「_com_error:: operator =」を参照してください。'
title: _com_error::operator =
ms.date: 11/04/2016
f1_keywords:
- _com_error::operator=
helpviewer_keywords:
- _com_error [C++]
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
ms.openlocfilehash: 3c27fcd612fcf2fd67b09ac1217286edd69e1557
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295797"
---
# <a name="_com_erroroperator-"></a>_com_error::operator =

**Microsoft 固有の仕様**

既存の `_com_error` オブジェクトを別のオブジェクトに割り当てます。

## <a name="syntax"></a>構文

```
_com_error& operator = (
   const _com_error& that
) throw ( );
```

#### <a name="parameters"></a>パラメーター

*that*<br/>
`_com_error` オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
