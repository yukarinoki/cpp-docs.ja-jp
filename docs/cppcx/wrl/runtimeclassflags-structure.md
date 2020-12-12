---
description: '詳細については、次を参照してください: RuntimeClassFlags 構造体'
title: RuntimeClassFlags 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 7874447fbbbe429884c5a79d0c70bb93e617ec61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209270"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 構造体

[RuntimeClass](runtimeclass-class.md)のインスタンスの型を格納します。

## <a name="syntax"></a>構文

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
[RuntimeClassType 列挙](runtimeclasstype-enumeration.md)値。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[RuntimeClassFlags::value 定数](#value-constant)|[RuntimeClassType 列挙](runtimeclasstype-enumeration.md)値が含まれています。|

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassFlags`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a> RuntimeClassFlags:: value 定数

[RuntimeClassType 列挙](runtimeclasstype-enumeration.md)値を含むフィールドです。

```cpp
static const unsigned int value = flags;
```
