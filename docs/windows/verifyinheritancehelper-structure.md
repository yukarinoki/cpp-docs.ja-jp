---
title: VerifyInheritanceHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs:
- C++
helpviewer_keywords:
- VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ddd358c3eb20439f87de8614d80af01537ae31e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396574"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename I,
   typename Base
>
struct VerifyInheritanceHelper;
template <
   typename I
>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>パラメーター

*I*<br/>
型。

*ベース*<br/>
別の型。

## <a name="remarks"></a>Remarks

1 つのインターフェイスが別のインターフェイスから派生したかどうかをテストします。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[VerifyInheritanceHelper::Verify メソッド](../windows/verifyinheritancehelper-verify-method.md)|現在のテンプレート パラメーターで指定された 2 つのインターフェイスをテストし、1 つのインターフェイスは、その他から派生されているかどうかを決定します。|

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInheritanceHelper`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)