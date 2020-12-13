---
description: 詳細については、「_com_error::D e)」を参照してください。
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: 6404d16361abe81d9e234a6b63039a7476d91ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332548"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Microsoft 固有の仕様**

`IErrorInfo::GetDescription` 関数を呼び出します。

## <a name="syntax"></a>構文

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>戻り値

オブジェクト内に記録されたオブジェクトのの結果を返し `IErrorInfo::GetDescription` `IErrorInfo` `_com_error` ます。 結果の `BSTR` は `_bstr_t` オブジェクトにカプセル化されます。 が記録されていない場合は、空のを `IErrorInfo` 返し `_bstr_t` ます。

## <a name="remarks"></a>解説

関数を呼び出し、 `IErrorInfo::GetDescription` `IErrorInfo` オブジェクト内に記録されたを取得し `_com_error` ます。 メソッドの呼び出し中に発生したエラー `IErrorInfo::GetDescription` はすべて無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
