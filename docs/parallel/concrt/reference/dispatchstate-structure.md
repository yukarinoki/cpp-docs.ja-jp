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
ms.openlocfilehash: 4c15fc0ba9c78d8b6416cd88480c8ada6e3febf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603564"
---
# <a name="dispatchstate-structure"></a>DispatchState 構造体

`DispatchState` 構造体は、状態を `IExecutionContext::Dispatch` メソッドに転送するために使用されます。 `Dispatch` メソッドが `IExecutionContext` インターフェイスで呼び出される状況を示します。

## <a name="syntax"></a>構文

```
struct DispatchState;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[DispatchState::DispatchState](#ctor)|新しい `DispatchState` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|バージョン管理に使用されるこの構造体のサイズ。|
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|このコンテキストが入力したかどうかを指示、`Dispatch`メソッド以前のコンテキストが非同期的にブロックされているためです。 UMS のスケジュール コンテキストでのみ使用され、値に設定されているこの`0`他のすべての実行コンテキスト。|
|[DispatchState::m_reserved](#m_reserved)|将来の情報を渡すために予約されたビット。|

## <a name="inheritance-hierarchy"></a>継承階層

`DispatchState`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="ctor"></a>  Dispatchstate::dispatchstate コンス トラクター

新しい `DispatchState` オブジェクトを構築します。

```
DispatchState();
```

##  <a name="m_dispatchstatesize"></a>  Dispatchstate::m_dispatchstatesize データ メンバー

バージョン管理に使用されるこの構造体のサイズ。

```
unsigned long m_dispatchStateSize;
```

##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  DispatchState::m_fIsPreviousContextAsynchronouslyBlocked Data Member

このコンテキストが入力したかどうかを指示、`Dispatch`メソッド以前のコンテキストが非同期的にブロックされているためです。 UMS のスケジュール コンテキストでのみ使用され、値に設定されているこの`0`他のすべての実行コンテキスト。

```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

##  <a name="m_reserved"></a>  Dispatchstate::m_reserved データ メンバー

将来の情報を渡すために予約されたビット。

```
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
