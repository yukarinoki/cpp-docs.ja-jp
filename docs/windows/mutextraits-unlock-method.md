---
title: Mutextraits::unlock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 7c4e5664-6d95-498a-95bb-d30b5e866c2c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e5f87a0daa13d26775f105b36a1fc076270af705
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608255"
---
# <a name="mutextraitsunlock-method"></a>MutexTraits::Unlock メソッド

共有リソースの排他的制御を解放します。

## <a name="syntax"></a>構文

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*h*  
ミュー テックス オブジェクトへのハンドルします。

## <a name="return-value"></a>戻り値

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[MutexTraits 構造体](../windows/mutextraits-structure.md)