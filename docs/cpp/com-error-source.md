---
title: _com_error::Source |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Source
dev_langs:
- C++
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69baf10012a461d60c6e7ae2d95a523ec725c255
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116543"
---
# <a name="comerrorsource"></a>_com_error::Source

**Microsoft 固有の仕様**

`IErrorInfo::GetSource` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t Source() const;
```

## <a name="return-value"></a>戻り値

結果を返します`IErrorInfo::GetSource`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は`IErrorInfo`が記録されると、空を返します`_bstr_t`します。

## <a name="remarks"></a>Remarks

呼び出すときの失敗、`IErrorInfo::GetSource`メソッドは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)