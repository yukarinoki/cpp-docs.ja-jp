---
description: '詳細については、次を参照してください: DispatchState 構造体'
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
ms.openlocfilehash: 1352a283d6f75d90872e75da92450a4867cf497f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169425"
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
|[DispatchState::D ispatchState](#ctor)|新しい `DispatchState` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|この構造体のサイズ。バージョン管理に使用されます。|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|`Dispatch`前のコンテキストが非同期的にブロックされているために、このコンテキストがメソッドに入ったかどうかを示します。 これは、UMS スケジューリングコンテキストでのみ使用され、 `0` 他のすべての実行コンテキストの値に設定されます。|
|[DispatchState:: m_reserved](#m_reserved)|将来の情報を渡すために予約されているビット。|

## <a name="inheritance-hierarchy"></a>継承階層

`DispatchState`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a> DispatchState::D ispatchState コンストラクター

新しい `DispatchState` オブジェクトを構築します。

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a> DispatchState:: m_dispatchStateSize データメンバー

この構造体のサイズ。バージョン管理に使用されます。

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a> DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked データメンバー

`Dispatch`前のコンテキストが非同期的にブロックされているために、このコンテキストがメソッドに入ったかどうかを示します。 これは、UMS スケジューリングコンテキストでのみ使用され、 `0` 他のすべての実行コンテキストの値に設定されます。

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a> DispatchState:: m_reserved データメンバー

将来の情報を渡すために予約されているビット。

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
