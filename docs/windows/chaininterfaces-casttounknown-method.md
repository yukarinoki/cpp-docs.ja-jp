---
title: Chaininterfaces::casttounknown メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96e7428e2263beb57eb73e024815000d61e75d5f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612558"
---
# <a name="chaininterfacescasttounknown-method"></a>ChainInterfaces::CastToUnknown メソッド

によって定義された型のインターフェイス ポインターをキャスト、 *I0*へのポインターをテンプレート パラメーター`IUnknown`します。

## <a name="syntax"></a>構文

```cpp
__forceinline IUnknown* CastToUnknown();
```

## <a name="return-value"></a>戻り値

ポインター`IUnknown`します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)