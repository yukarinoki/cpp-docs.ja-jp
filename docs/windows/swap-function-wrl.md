---
title: Swap 関数 (WRL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Swap
dev_langs:
- C++
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32efd35d162413de75d4e68c54593f03406aba0d
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250972"
---
# <a name="swap-function-wrl"></a>Swap 関数 (WRL)

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW inline void Swap(
   _Inout_ T& left,
   _Inout_ T& right
);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
最初の引数。

*right*<br/>
2 番目の引数。

## <a name="return-value"></a>戻り値

## <a name="remarks"></a>Remarks

指定された 2 つの引数の値を交換します。

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)