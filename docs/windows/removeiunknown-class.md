---
title: RemoveIUnknown クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
dev_langs:
- C++
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81892b624425032c8f0e69fe667ad24026c40ca4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410270"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown クラス

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename T
>
struct RemoveIUnknown;

template <
   typename T
>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
クラス。

## <a name="remarks"></a>Remarks

等価の型を作成、 `IUnknown`-ベースの型が、非仮想`QueryInterface`、 `AddRef`、および`Release`メンバー関数。

既定では、COM メソッドを提供仮想`QueryInterface`、 `AddRef`、および`Release`メソッド。 ただし、`ComPtr`仮想メソッドのオーバーヘッドは必要ありません。 `RemoveIUnknown` プライベートの非仮想を提供することでそのオーバーヘッドを排除`QueryInterface`、 `AddRef`、および`Release`メソッド。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`ReturnType`|テンプレート パラメーターに相当する型のシノニム*T*が非仮想`IUnknown`メンバー。|

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`RemoveIUnknown`

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)