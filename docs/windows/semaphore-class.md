---
title: クラスのセマフォ |Microsoft Docs
ms.custom: ''
ms.date: 09/25/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 269b3229a0755e88d55fc4fa5d14b843345ccc44
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234454"
---
# <a name="semaphore-class"></a>Semaphore クラス

ユーザーの数に制限をサポートできる共有リソースを制御する同期オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前       | 説明
---------- | ------------------------------------------------------
`SyncLock` | 同期ロックをサポートするクラスのシノニムです。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | ----------------------------------------------------
[Semaphore::semaphore](#semaphore) | `Semaphore` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                     | 説明
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semaphore::lock](#lock) | シグナルの状態にある現在のオブジェクトまたは指定したハンドルに関連付けられたオブジェクトまでの待機、または指定されたタイムアウト期間が経過しました。

### <a name="public-operators"></a>パブリック演算子

名前                                     | 説明
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semaphore::operator =](#operator-assign) | 指定したハンドルの移動、`Semaphore`現在オブジェクト`Semaphore`オブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`Semaphore`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="lock"></a>Semaphore::lock

現在のオブジェクトまでの待機、または`Semaphore`オブジェクトに関連付けられている指定したハンドルがシグナル状態で、または指定されたタイムアウト期間が経過しました。

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>パラメーター

*(ミリ秒)*<br/>
タイムアウト間隔 (ミリ秒単位)。 既定値は、INFINITE で、無期限に待機します。

*h*<br/>
識別するハンドルを`Semaphore`オブジェクト。

### <a name="return-value"></a>戻り値

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`。

## <a name="operator-assign"></a>Semaphore::operator =

指定したハンドルの移動、`Semaphore`現在オブジェクト`Semaphore`オブジェクト。

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
右辺値参照を`Semaphore`オブジェクト。

### <a name="return-value"></a>戻り値

現在への参照を`Semaphore`オブジェクト。

## <a name="semaphore"></a>Semaphore::semaphore

`Semaphore` クラスの新しいインスタンスを初期化します。

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドルまたはへの右辺値参照を`Semaphore`オブジェクト。
