---
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
ms.openlocfilehash: 6d4ba08ab1884e8584b0e98e931d2d63cdac5aec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371249"
---
# <a name="mutextraits-structure"></a>MutexTraits 構造体

[Mutex](mutex-class.md)クラスの共通の特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                           | 説明
------------------------------ | ------------------------------------------------
[ミューテックストレイツ::ロック解除](#unlock) | 共有リソースの排他制御を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="mutextraitsunlock-method"></a><a name="unlock"></a>ミューテックストレイツ::ロック解除方法

共有リソースの排他制御を解放します。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
ミューテックス オブジェクトへのハンドル。
