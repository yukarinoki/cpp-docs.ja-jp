---
title: ArgTraitsHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb0377de88ef5e782e0e11bc563409b7094eecf5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598685"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*  
デリゲートのインターフェイスです。

## <a name="remarks"></a>Remarks

定義のデリゲート引数の一般的な特性に役立ちます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`methodType`|`decltype(&TDelegateInterface::Invoke)` と同義。|
|`Traits`|`ArgTraits<methodType>` と同義。|

### <a name="public-constants"></a>パブリック定数

|name|説明|
|----------|-----------------|
|[ArgTraitsHelper::args 定数](../windows/argtraitshelper-args-constant.md)|により、 [argtraits::args](../windows/argtraits-args-constant.md)パラメーターの数のカウントを保持、`Invoke`デリゲート インターフェイスのメソッド。|

## <a name="inheritance-hierarchy"></a>継承階層

`ArgTraitsHelper`

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)