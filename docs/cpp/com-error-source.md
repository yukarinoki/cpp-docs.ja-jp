---
description: '詳細については、「_com_error:: Source」を参照してください。'
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 3b6cf35420454e8285d3d8b4deee3df8fe8771e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295771"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Microsoft 固有の仕様**

`IErrorInfo::GetSource` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t Source() const;
```

## <a name="return-value"></a>戻り値

オブジェクト内に記録されたオブジェクトのの結果を返し `IErrorInfo::GetSource` `IErrorInfo` `_com_error` ます。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 が記録されていない場合は、空のを `IErrorInfo` 返し `_bstr_t` ます。

## <a name="remarks"></a>解説

メソッドの呼び出し中に発生したエラー `IErrorInfo::GetSource` はすべて無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
