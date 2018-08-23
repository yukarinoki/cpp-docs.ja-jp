---
title: Asyncbase::get_status メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Status
dev_langs:
- C++
helpviewer_keywords:
- get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31b333c14af6d57fb098d6aff0d0938092477de0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613125"
---
# <a name="asyncbasegetstatus-method"></a>AsyncBase::get_Status メソッド

非同期操作の状態を示す値を取得します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>パラメーター

*status*  
状態が格納される場所です。 詳細については、次を参照してください。`Windows::Foundation::AsyncStatus`列挙体。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="remarks"></a>Remarks

このメソッドは、`IAsyncInfo::get_Status` を実装します。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)