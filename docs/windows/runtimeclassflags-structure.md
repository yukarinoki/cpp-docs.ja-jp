---
title: RuntimeClassFlags 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c3cb141576598aa39c718316048900622c4df41
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691459"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 構造体

インスタンスの型が含まれています、 [RuntimeClass](../windows/runtimeclass-class.md)します。

## <a name="syntax"></a>構文

```cpp
template <
   unsigned int flags
>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>パラメーター

*flags*  
A [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[RuntimeClassFlags::value 定数](#value-constant)|含まれています、 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。|

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassFlags`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="value-constant"></a>Runtimeclassflags::value 定数

含むフィールドを[RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。
  
```cpp
static const unsigned int value = flags;
```
