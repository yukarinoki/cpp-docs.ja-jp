---
title: _com_error::ErrorInfo |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc2906827e6a465106a3dbdcb8b63c7b53a39ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039349"
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 固有の仕様**

コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。

## <a name="syntax"></a>構文

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>戻り値

コンストラクターに渡された未処理の `IErrorInfo` 項目。

## <a name="remarks"></a>Remarks

カプセル化された取得`IErrorInfo`内の項目を`_com_error`オブジェクト、または、ない場合は NULL`IErrorInfo`項目が記録されます。 呼び出し元が呼び出す必要があります`Release`完了すると、返されたオブジェクトを使用します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)