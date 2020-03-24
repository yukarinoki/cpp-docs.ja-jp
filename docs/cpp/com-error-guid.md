---
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: d5b05cd4e26f89d42ea23b605f5e6560795a0cfa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180642"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Microsoft 固有の仕様**

`IErrorInfo::GetGUID` 関数を呼び出します。

## <a name="syntax"></a>構文

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>戻り値

`_com_error` オブジェクト内に記録された `IErrorInfo` オブジェクトの `IErrorInfo::GetGUID` の結果を返します。 `IErrorInfo` オブジェクトが記録されていない場合は `GUID_NULL`を返します。

## <a name="remarks"></a>解説

`IErrorInfo::GetGUID` メソッドの呼び出し中に発生したエラーは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
