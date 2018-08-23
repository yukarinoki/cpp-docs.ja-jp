---
title: RemoveReference 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
dev_langs:
- C++
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d73c9f99eec3fd3ec01d4ae5d41418c67cb472f9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597466"
---
# <a name="removereference-structure"></a>RemoveReference 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<class T>
struct RemoveReference;
template<class T>
struct RemoveReference<T&>;
template<class T>
struct RemoveReference<T&&>;
```

### <a name="parameters"></a>パラメーター

*T*  
クラス。

## <a name="remarks"></a>Remarks

指定されたクラス テンプレートのパラメーターから参照または右辺値参照の特徴を取り除きます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`Type`|クラス テンプレート パラメーターのシノニム。|

## <a name="inheritance-hierarchy"></a>継承階層

`RemoveReference`

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)