---
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: b3c79bb069ef504680e83359d6ec90c803f16d9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180590"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Microsoft 固有の仕様**

`IErrorInfo::GetHelpContext` 関数を呼び出します。

## <a name="syntax"></a>構文

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>戻り値

`_com_error` オブジェクト内に記録された `IErrorInfo` オブジェクトの `IErrorInfo::GetHelpContext` の結果を返します。 `IErrorInfo` オブジェクトが記録されない場合は、0を返します。

## <a name="remarks"></a>解説

`IErrorInfo::GetHelpContext` メソッドの呼び出し中に発生したエラーは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
