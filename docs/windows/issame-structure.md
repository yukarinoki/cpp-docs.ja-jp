---
title: IsSame 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
dev_langs:
- C++
helpviewer_keywords:
- IsSame structure
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e9e45f64d8eda3e24fb7c85120f14e981963f7f1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595786"
---
# <a name="issame-structure"></a>IsSame 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename T1,
   typename T2
>
struct IsSame;
template <
   typename T1
>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>パラメーター

*T1*  
型。

*T2*  
別の型。

## <a name="remarks"></a>Remarks

別のと同じ型を指定した 1 つかどうかがテストには、種類が指定されました。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

|name|説明|
|----------|-----------------|
|[IsSame::value 定数](../windows/issame-value-constant.md)|1 つの型が別のと同じかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`IsSame`

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)