---
title: _com_error::operator = |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= _com_error objects
- = operator [C++], with specific Visual C++ objects
- operator = _com_error objects
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2fe53c7040bc248d63bd3d14f90f915bdcd689a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061033"
---
# <a name="comerroroperator-"></a>_com_error::operator =

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

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)