---
description: '詳細については、「_com_error:: HelpFile」を参照してください。'
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: e45785913a8a5a1909f702bce672727171e0baef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295927"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Microsoft 固有の仕様**

`IErrorInfo::GetHelpFile` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>戻り値

オブジェクト内に記録されたオブジェクトのの結果を返し `IErrorInfo::GetHelpFile` `IErrorInfo` `_com_error` ます。 結果の BSTR は `_bstr_t` オブジェクトにカプセル化されます。 が記録されていない場合は、空のを `IErrorInfo` 返し `_bstr_t` ます。

## <a name="remarks"></a>解説

メソッドの呼び出し中に発生したエラー `IErrorInfo::GetHelpFile` はすべて無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
