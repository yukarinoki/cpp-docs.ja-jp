---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: de2275f096fe2fde96e64cbc3034602a1fde5e88
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180772"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Microsoft 固有の仕様**

`IErrorInfo::GetDescription` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>戻り値

`_com_error` オブジェクト内に記録された `IErrorInfo` オブジェクトの `IErrorInfo::GetDescription` の結果を返します。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 `IErrorInfo` が記録されていない場合は、空の `_bstr_t`を返します。

## <a name="remarks"></a>解説

`IErrorInfo::GetDescription` 関数を呼び出し、`_com_error` オブジェクト内に記録された `IErrorInfo` を取得します。 `IErrorInfo::GetDescription` メソッドの呼び出し中に発生したエラーは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
