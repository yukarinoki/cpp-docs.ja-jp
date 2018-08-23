---
title: AsyncStatusInternal 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b389e5b137ef3cdb94ffbb1fc381ebe2e5813963
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603971"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Remarks

非同期操作の状態の内部列挙値の間のマッピングを指定します、`Windows::Foundation::AsyncStatus`列挙体。

## <a name="members"></a>メンバー

`_Created`  
`::Windows::Foundation::AsyncStatus::Created` と同じ意味です。

`_Started`  
`::Windows::Foundation::AsyncStatus::Started` と同じ意味です。

`_Completed`  
`::Windows::Foundation::AsyncStatus::Completed` と同じ意味です。

`_Cancelled`  
`::Windows::Foundation::AsyncStatus::Cancelled` と同じ意味です。

`_Error`  
`::Windows::Foundation::AsyncStatus::Error` と同じ意味です。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)