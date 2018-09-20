---
title: DerefHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 016f6c5effeb964d5682f0a83ef63a4884b324c6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388499"
---
# <a name="derefhelper-structure"></a>DerefHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename T
>
struct DerefHelper;

template <
   typename T
>
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