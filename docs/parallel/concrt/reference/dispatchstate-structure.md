---
title: DispatchState 構造体
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 2c4103f89f7fc74c5368bafac3c82685ff9b6e03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372699"
---
# <a name="dispatchstate-structure"></a>DispatchState 構造体

`DispatchState` 構造体は、状態を `IExecutionContext::Dispatch` メソッドに転送するために使用されます。 `Dispatch` メソッドが `IExecutionContext` インターフェイスで呼び出される状況を示します。

## <a name="syntax"></a>構文

```cpp
struct DispatchState;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ディスパッチステート::Dパッチステート](#ctor)|新しい `DispatchState` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ディスパッチステート::m_dispatchStateSize](#m_dispatchstatesize)|バージョン管理に使用されるこの構造体のサイズ。|
|[ディスパッチステート::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|前のコンテキストが非同期にブロック`Dispatch`されたために、このコンテキストがメソッドに入ったかどうかを示します。 これは UMS スケジューリング コンテキストでのみ使用され、その他のすべての実行コンテキスト`0`の値に設定されます。|
|[ディスパッチステート::m_reserved](#m_reserved)|将来の情報渡し用に予約されたビット。|

## <a name="inheritance-hierarchy"></a>継承階層

`DispatchState`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>ディスパッチステート::Dシスパッチステートコンストラクタ

新しい `DispatchState` オブジェクトを構築します。

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>ディスパッチステート::m_dispatchStateSizeデータメンバー

バージョン管理に使用されるこの構造体のサイズ。

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>ディスパッチステート::m_fIsPreviousContextAsynchronouslyBlockedデータメンバー

前のコンテキストが非同期にブロック`Dispatch`されたために、このコンテキストがメソッドに入ったかどうかを示します。 これは UMS スケジューリング コンテキストでのみ使用され、その他のすべての実行コンテキスト`0`の値に設定されます。

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a>ディスパッチステート::m_reservedデータメンバー

将来の情報渡し用に予約されたビット。

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)
