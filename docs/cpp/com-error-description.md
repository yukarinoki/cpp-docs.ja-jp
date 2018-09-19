---
title: _com_error::Description |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90208866ee08d6990d8f1b5322a38fbd2d63a651
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091791"
---
# <a name="comerrordescription"></a>_com_error::Description

**Microsoft 固有の仕様**

`IErrorInfo::GetDescription` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>戻り値

結果を返します`IErrorInfo::GetDescription`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は`IErrorInfo`が記録されると、空を返します`_bstr_t`します。

## <a name="remarks"></a>Remarks

呼び出し、`IErrorInfo::GetDescription`関数を取得します`IErrorInfo`内に記録された、`_com_error`オブジェクト。 呼び出すときの失敗、`IErrorInfo::GetDescription`メソッドは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)