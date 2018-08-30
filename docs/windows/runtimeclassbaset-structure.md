---
title: RuntimeClassBaseT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d137281d7f573275b216eecaea9e4f09564b9f6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206552"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   unsigned int RuntimeClassTypeT
>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>パラメーター

*RuntimeClassTypeT*  
1 つまたは複数を指定するフラグのフィールド[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙子。

## <a name="remarks"></a>Remarks

ヘルパー メソッドを提供します`QueryInterface`操作とのインターフェイス Id を取得します。

## <a name="members"></a>メンバー

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassBaseT`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[リファレンス (Windows ランタイム ライブラリ)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)