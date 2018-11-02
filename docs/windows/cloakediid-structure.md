---
title: CloakedIid 構造体
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 7340032e91a9b30b72099477b55b88740b3eb68f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535305"
---
# <a name="cloakediid-structure"></a>CloakedIid 構造体

示します、 `RuntimeClass`、`Implements`と`ChainInterfaces`テンプレートの指定したインターフェイスが IID リストにアクセスできないことです。

## <a name="syntax"></a>構文

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
インターフェイスが非表示 (クロークされています)。

## <a name="remarks"></a>Remarks

方法の例を次に**CloakedIid**使用:`struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`します。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`CloakedIid`

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)