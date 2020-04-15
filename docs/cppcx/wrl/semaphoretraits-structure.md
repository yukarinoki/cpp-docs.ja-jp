---
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
ms.openlocfilehash: 11719576c9fc7b23f4cd318ee1b3ed9ca3f5edaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360736"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits 構造体

オブジェクトの共通の特性`Semaphore`を定義します。

## <a name="syntax"></a>構文

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                               | 説明
---------------------------------- | --------------------------------------
[セマフォ海峡::ロック解除](#unlock) | 共有リソースの制御を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a>セマフォ海峡::ロック解除

共有リソースの制御を解放します。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`Semaphore`オブジェクトへのハンドル。

### <a name="remarks"></a>解説

ロック解除操作が失敗した場合`Unlock()`は、失敗の原因を示すエラーを出力します。
