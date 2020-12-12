---
description: '詳細については、「_com_error:: ErrorInfo」を参照してください。'
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 36092ae9287352d421bf502ad24c054cf3b7a907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296044"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 固有の仕様**

コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。

## <a name="syntax"></a>構文

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>戻り値

コンストラクターに渡された未処理の `IErrorInfo` 項目。

## <a name="remarks"></a>解説

オブジェクト内のカプセル化された項目を取得し `IErrorInfo` `_com_error` `IErrorInfo` ます。項目が記録されていない場合は NULL を取得します。 呼び出し元は、 `Release` 使用が終了したときに、返されたオブジェクトに対してを呼び出す必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
