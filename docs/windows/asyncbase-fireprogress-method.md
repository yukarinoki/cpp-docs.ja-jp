---
title: Asyncbase::fireprogress メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91cf005e3dc1d088a5c7d0e664f67610fac28843
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606250"
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress メソッド

現在の進行状況イベント ハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>パラメーター

*arg*  
呼び出すイベント ハンドラー メソッド。

## <a name="remarks"></a>Remarks

`ProgressTraits` 派生[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)