---
description: '詳細情報: SRWLock クラス'
title: SRWLock クラス
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: 10bc3dc700f90d5154ece1546cdf3ec464ea6e56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135188"
---
# <a name="srwlock-class"></a>SRWLock クラス

スリムリーダー/ライターロックを表します。

## <a name="syntax"></a>構文

```cpp
class SRWLock;
```

## <a name="remarks"></a>解説

スリムリーダー/ライターロックは、スレッド間のアクセスをオブジェクトまたはリソースに同期するために使用されます。 詳細については、「 [同期関数](/windows/win32/Sync/synchronization-functions)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前                | 説明
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | `SRWLock`排他モードで取得されるオブジェクトのシノニム。
`SyncLockShared`    | `SRWLock`共有モードで取得されるオブジェクトのシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                     | 説明
---------------------------------------- | --------------------------------------------------
[SRWLock:: SRWLock](#srwlock-constructor) | `SRWLock` クラスの新しいインスタンスを初期化します。
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | クラスのインスタンスを初期化解除 `SRWLock` します。

### <a name="public-methods"></a>パブリック メソッド

名前                                           | 説明
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock:: LockExclusive](#lockexclusive)       | `SRWLock`排他モードでオブジェクトを取得します。
[SRWLock:: LockShared](#lockshared)             | `SRWLock`共有モードでオブジェクトを取得します。
[SRWLock:: TryLockExclusive](#trylockexclusive) | `SRWLock`現在のオブジェクトまたは指定されたオブジェクトに対して、排他モードでのオブジェクトの取得を試み `SRWLock` ます。
[SRWLock:: TryLockShared](#trylockshared)       | `SRWLock`現在のオブジェクトまたは指定されたオブジェクトについて、共有モードのオブジェクトの取得を試み `SRWLock` ます。

### <a name="protected-data-member"></a>保護されるデータメンバー

名前                                      | 説明
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock:: SRWLock_](#srwlock-data-member) | 現在のオブジェクトの基になるロック変数を格納し `SRWLock` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLock`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a> SRWLock:: ~ SRWLock

クラスのインスタンスを初期化解除 `SRWLock` します。

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a> SRWLock:: LockExclusive

`SRWLock`排他モードでオブジェクトを取得します。

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
オブジェクトへのポインター `SRWLock` 。

### <a name="return-value"></a>戻り値

`SRWLock`排他モードのオブジェクト。

## <a name="srwlocklockshared"></a><a name="lockshared"></a> SRWLock:: LockShared

`SRWLock`共有モードでオブジェクトを取得します。

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
オブジェクトへのポインター `SRWLock` 。

### <a name="return-value"></a>戻り値

`SRWLock`共有モードのオブジェクトです。

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a> SRWLock:: SRWLock

`SRWLock` クラスの新しいインスタンスを初期化します。

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a> SRWLock:: SRWLock_

現在のオブジェクトの基になるロック変数を格納し `SRWLock` ます。

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a> SRWLock:: TryLockExclusive

`SRWLock`現在のオブジェクトまたは指定されたオブジェクトに対して、排他モードでのオブジェクトの取得を試み `SRWLock` ます。 呼び出しが成功すると、呼び出し元のスレッドはロックの所有権を取得します。

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
オブジェクトへのポインター `SRWLock` 。

### <a name="return-value"></a>戻り値

成功した場合、 `SRWLock` 排他モードのオブジェクトと呼び出し元のスレッドは、ロックの所有権を取得します。 それ以外の場合は、 `SRWLock` 状態が無効であるオブジェクト。

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a> SRWLock:: TryLockShared

`SRWLock`現在のオブジェクトまたは指定されたオブジェクトについて、共有モードのオブジェクトの取得を試み `SRWLock` ます。

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
オブジェクトへのポインター `SRWLock` 。

### <a name="return-value"></a>戻り値

成功すると、 `SRWLock` 共有モードのオブジェクトと呼び出し元のスレッドが、ロックの所有権を取得します。 それ以外の場合は、 `SRWLock` 状態が無効であるオブジェクト。
