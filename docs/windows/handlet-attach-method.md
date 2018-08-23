---
title: Handlet::attach メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80918d2ab783472b37a9739045fd7539a92bd3e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605633"
---
# <a name="handletattach-method"></a>HandleT::Attach メソッド

現在の指定したハンドルに関連付けます**HandleT**オブジェクト。

## <a name="syntax"></a>構文

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

#### <a name="parameters"></a>パラメーター

*h*  
ハンドル。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HandleT クラス](../windows/handlet-class.md)