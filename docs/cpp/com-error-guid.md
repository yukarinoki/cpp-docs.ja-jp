---
title: _com_error::GUID |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f63d81fa8550bd9cbb7c051803c0d1e891cefe15
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031058"
---
# <a name="comerrorguid"></a>_com_error::GUID

**Microsoft 固有の仕様**

`IErrorInfo::GetGUID` 関数を呼び出します。

## <a name="syntax"></a>構文

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>戻り値

結果を返します`IErrorInfo::GetGUID`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 ない場合は`IErrorInfo`返しますオブジェクトが記録されて、`GUID_NULL`します。

## <a name="remarks"></a>Remarks

呼び出すときの失敗、`IErrorInfo::GetGUID`メソッドは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)