---
title: Asyncbase::currentstatus メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 792f9f6c6d76097459498c43068f46d86b2e2349
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401486"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus メソッド

現在の非同期操作の状態を取得します。

## <a name="syntax"></a>構文

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この操作が現在の状態を格納する場所です。

## <a name="remarks"></a>Remarks

この操作は、スレッド セーフです。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)<br/>
[AsyncStatusInternal 列挙型](../windows/asyncstatusinternal-enumeration.md)