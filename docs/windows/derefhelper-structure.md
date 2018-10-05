---
title: DerefHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
dev_langs:
- C++
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d9339256d4dfda717d52b11da965b3600a53cd1
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788358"
---
# <a name="derefhelper-structure"></a>DerefHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
テンプレート パラメーター。

## <a name="remarks"></a>Remarks

逆参照されたポインターを表す、`T*`テンプレート パラメーター。

**DerefHelper**など、式で使用されます。`ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`DerefType`|逆参照されるテンプレート パラメーターの識別子の`T*`します。|

## <a name="inheritance-hierarchy"></a>継承階層

`DerefHelper`

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)