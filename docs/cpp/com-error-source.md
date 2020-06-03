---
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 43dd21297ddd54863d535402dddd59243d589eec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180525"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Microsoft 固有の仕様**

`IErrorInfo::GetSource` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t Source() const;
```

## <a name="return-value"></a>戻り値

`_com_error` オブジェクト内に記録された `IErrorInfo` オブジェクトの `IErrorInfo::GetSource` の結果を返します。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 `IErrorInfo` が記録されていない場合は、空の `_bstr_t`を返します。

## <a name="remarks"></a>解説

`IErrorInfo::GetSource` メソッドの呼び出し中に発生したエラーは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
