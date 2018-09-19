---
title: _com_error::HelpFile |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f40ea4dd39e88508e6e12c9d7103b7a536902d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070555"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile

**Microsoft 固有の仕様**

`IErrorInfo::GetHelpFile` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>戻り値

結果を返します`IErrorInfo::GetHelpFile`の`IErrorInfo`内オブジェクトに記録された、`_com_error`オブジェクト。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 ない場合は`IErrorInfo`が記録されると、空を返します`_bstr_t`します。

## <a name="remarks"></a>Remarks

呼び出すときの失敗、`IErrorInfo::GetHelpFile`メソッドは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)