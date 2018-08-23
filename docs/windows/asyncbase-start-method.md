---
title: Asyncbase::start メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81a3f29e99f49b03eb76f44af60c42d433e0bdc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611233"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start メソッド

非同期操作を開始します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(
   Start
)(void);
```

## <a name="return-value"></a>戻り値

S_OK 場合は、操作の開始またはが既に開始します。それ以外の場合、E_ILLEGAL_STATE_CHANGE します。

## <a name="remarks"></a>Remarks

**Start()** の既定の実装は、 `IAsyncInfo::Start`、実際の作業を行いません。 実際には、非同期操作を開始するには、オーバーライド、`OnStart()`純粋仮想メソッド。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)