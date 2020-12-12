---
description: '詳細については、「_com_error:: GUID」を参照してください。'
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 32f88728d5c0f93094413aaeae8fb3c116b415c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295966"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Microsoft 固有の仕様**

`IErrorInfo::GetGUID` 関数を呼び出します。

## <a name="syntax"></a>構文

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>戻り値

オブジェクト内に記録されたオブジェクトのの結果を返し `IErrorInfo::GetGUID` `IErrorInfo` `_com_error` ます。 `IErrorInfo`オブジェクトが記録されていない場合は、を返し `GUID_NULL` ます。

## <a name="remarks"></a>解説

メソッドの呼び出し中に発生したエラー `IErrorInfo::GetGUID` はすべて無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
