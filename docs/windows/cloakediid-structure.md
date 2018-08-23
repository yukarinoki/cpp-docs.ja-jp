---
title: CloakedIid 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a60d12adfade18c9989d1dc8609a38252d32073
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599099"
---
# <a name="cloakediid-structure"></a>CloakedIid 構造体

示します、 `RuntimeClass`、`Implements`と`ChainInterfaces`テンプレートの指定したインターフェイスが IID リストにアクセスできないことです。

## <a name="syntax"></a>構文

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>パラメーター

*T*  
インターフェイスが非表示 (クロークされています)。

## <a name="remarks"></a>Remarks

方法の例を次に**CloakedIid**使用:`struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`します。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`CloakedIid`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)