---
description: '詳細情報: _com_error:: HelpContext'
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: 757fb572d9e41486af419712eb7f70cd7cfa7b14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295940"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Microsoft 固有の仕様**

`IErrorInfo::GetHelpContext` 関数を呼び出します。

## <a name="syntax"></a>構文

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>戻り値

オブジェクト内に記録されたオブジェクトのの結果を返し `IErrorInfo::GetHelpContext` `IErrorInfo` `_com_error` ます。 `IErrorInfo`オブジェクトが記録されない場合は、0を返します。

## <a name="remarks"></a>解説

メソッドの呼び出し中に発生したエラー `IErrorInfo::GetHelpContext` はすべて無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
