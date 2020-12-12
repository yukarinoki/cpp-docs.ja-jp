---
description: '詳細: セマフォクラス'
title: Semaphore クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: 0cf99ff0a0e5263b3ed924ec5ac69b7edb0bd1f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186234"
---
# <a name="semaphore-class"></a>Semaphore クラス

限定された数のユーザーをサポートできる共有リソースを制御する同期オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前       | 説明
---------- | ------------------------------------------------------
`SyncLock` | 同期ロックをサポートするクラスのシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | ----------------------------------------------------
[セマフォ:: セマフォ](#semaphore) | `Semaphore` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                     | 説明
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[セマフォ:: Lock](#lock) | 現在のオブジェクト、または指定したハンドルに関連付けられているオブジェクトがシグナル状態になるか、指定されたタイムアウト間隔が経過するまで待機します。

### <a name="public-operators"></a>パブリック演算子

名前                                     | 説明
---------------------------------------- | ---------------------------------------------------------------------------------------
[セマフォ:: operator =](#operator-assign) | 指定したハンドルを `Semaphore` オブジェクトから現在のオブジェクトに移動 `Semaphore` します。

## <a name="inheritance-hierarchy"></a>継承階層

`Semaphore`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="semaphorelock"></a><a name="lock"></a> セマフォ:: Lock

現在のオブジェクト、または指定した `Semaphore` ハンドルに関連付けられているオブジェクトがシグナル状態になるか、指定されたタイムアウト間隔が経過するまで待機します。

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

*milliseconds*<br/>
タイムアウト間隔 (ミリ秒単位)。 既定値は無限で、無制限に待機します。

*h*<br/>
オブジェクトへのハンドル `Semaphore` 。

### <a name="return-value"></a>戻り値

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`。

## <a name="semaphoreoperator"></a><a name="operator-assign"></a> セマフォ:: operator =

指定したハンドルを `Semaphore` オブジェクトから現在のオブジェクトに移動 `Semaphore` します。

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
Rvalue-オブジェクトへの参照 `Semaphore` 。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照 `Semaphore` 。

## <a name="semaphoresemaphore"></a><a name="semaphore"></a> セマフォ:: セマフォ

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
オブジェクトへのハンドルまたは右辺値参照 `Semaphore` 。
