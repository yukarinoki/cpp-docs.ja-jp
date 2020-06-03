---
title: _com_error::operator =
ms.date: 11/04/2016
f1_keywords:
- _com_error::operator=
helpviewer_keywords:
- _com_error [C++]
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
ms.openlocfilehash: 7f24076a0286da910378d6633f483e6f050858b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180551"
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

*それ*<br/>
`_com_error` オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
