---
title: DontUseNewUseMake クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ce3e391ac0da93ed7571a95ce328a5260a8dd44
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593608"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake クラス

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Remarks

演算子を使用できないように**新しい**で`RuntimeClass`します。 したがって、使用する必要があります、[関数](../windows/make-function.md)代わりにします。

## <a name="members"></a>メンバー

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[DontUseNewUseMake::operator new 演算子](../windows/dontusenewusemake-operator-new-operator.md)|演算子をオーバー ロード**新しい**しで使用されていることを防ぎます`RuntimeClass`します。|

## <a name="inheritance-hierarchy"></a>継承階層

`DontUseNewUseMake`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)  
[Make 関数](../windows/make-function.md)