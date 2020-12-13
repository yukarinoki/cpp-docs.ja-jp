---
description: '詳細については、次を参照してください: CloakedIid 構造体'
title: CloakedIid 構造体
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 06bddded27882ae1216064aafc311364a8d2fd9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338792"
---
# <a name="cloakediid-structure"></a>CloakedIid 構造体

`RuntimeClass`、、 `Implements` および指定されたインターフェイスに `ChainInterfaces` IID リストでアクセスできないテンプレートを指定します。

## <a name="syntax"></a>構文

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
非表示 (クローク) されているインターフェイス。

## <a name="remarks"></a>解説

**CloakedIid** の使用方法の例を次に示します `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}` 。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`CloakedIid`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
