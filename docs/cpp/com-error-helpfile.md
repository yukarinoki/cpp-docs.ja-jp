---
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: 775adfa7d5dd5aca098edcd793c2164d65fe7efa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190223"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Microsoft 固有の仕様**

`IErrorInfo::GetHelpFile` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>戻り値

`_com_error` オブジェクト内に記録された `IErrorInfo` オブジェクトの `IErrorInfo::GetHelpFile` の結果を返します。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 `IErrorInfo` が記録されていない場合は、空の `_bstr_t`を返します。

## <a name="remarks"></a>解説

`IErrorInfo::GetHelpFile` メソッドの呼び出し中に発生したエラーは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
