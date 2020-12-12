---
description: '詳細については、次を参照してください: MutexTraits 構造体'
title: MutexTraits 構造体
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: e3dfcee1251794734ed5cf787096361403d80c7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330817"
---
# <a name="mutextraits-structure"></a>MutexTraits 構造体

[Mutex](mutex-class.md)クラスの一般的な特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                           | 説明
------------------------------ | ------------------------------------------------
[MutexTraits:: Unlock](#unlock) | 共有リソースの排他的な制御を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="mutextraitsunlock-method"></a><a name="unlock"></a> MutexTraits:: Unlock メソッド

共有リソースの排他的な制御を解放します。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
Mutex オブジェクトを処理します。
