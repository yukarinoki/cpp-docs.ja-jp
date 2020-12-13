---
description: '詳細については、次を参照してください: SemaphoreTraits 構造体'
title: SemaphoreTraits 構造体
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: 5779a30d22fd2d32e57f96f752bb52e2bf469cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135227"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits 構造体

オブジェクトの一般的な特性を定義 `Semaphore` します。

## <a name="syntax"></a>構文

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                               | 説明
---------------------------------- | --------------------------------------
[SemaphoreTraits:: Unlock](#unlock) | 共有リソースの制御を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a> SemaphoreTraits:: Unlock

共有リソースの制御を解放します。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
オブジェクトをハンドル `Semaphore` します。

### <a name="remarks"></a>解説

ロック解除操作が失敗した場合、は `Unlock()` エラーの原因を示すエラーを出力します。
