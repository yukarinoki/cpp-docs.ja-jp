---
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
ms.openlocfilehash: e305ad54e30455ce7c25f356c454791da0783591
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377275"
---
# <a name="srwlock-class"></a>SRWLock クラス

スリム リーダー/ライター ロックを表します。

## <a name="syntax"></a>構文

```cpp
class SRWLock;
```

## <a name="remarks"></a>解説

スリム リーダー/ライター ロックは、オブジェクトまたはリソースへのスレッド間のアクセスを同期するために使用されます。 詳細については、「[同期関数](/windows/win32/Sync/synchronization-functions)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前                | 説明
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | 排他モード`SRWLock`で取得されたオブジェクトのシノニム。
`SyncLockShared`    | 共有モードで`SRWLock`取得されたオブジェクトのシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                     | 説明
---------------------------------------- | --------------------------------------------------
[SRWロック::SRWロック](#srwlock-constructor) | `SRWLock` クラスの新しいインスタンスを初期化します。
[SRWロック::~SRWロック](#tilde-srwlock)      | クラスのインスタンスを初期化解除します`SRWLock`。

### <a name="public-methods"></a>パブリック メソッド

名前                                           | 説明
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWロック::ロックエクスクルーシブ](#lockexclusive)       | 排他モード`SRWLock`でオブジェクトを取得します。
[SRWロック::ロックシェアード](#lockshared)             | 共有モードで`SRWLock`オブジェクトを取得します。
[SRWロック::トリロックエクスクルーシブ](#trylockexclusive) | 現在のオブジェクトまたは指定`SRWLock`した`SRWLock`オブジェクトの排他モードでオブジェクトを取得しようとします。
[SRWロック::トライロックシェア](#trylockshared)       | 現在のオブジェクトまたは指定`SRWLock`した`SRWLock`オブジェクトの共有モードでオブジェクトを取得しようとします。

### <a name="protected-data-member"></a>保護されたデータ メンバー

名前                                      | 説明
----------------------------------------- | -----------------------------------------------------------------------
[SRWロック::SRWLock_](#srwlock-data-member) | 現在`SRWLock`のオブジェクトの基になるロック変数を格納します。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLock`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a>SRWロック::~SRWロック

クラスのインスタンスを初期化解除します`SRWLock`。

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a>SRWロック::ロックエクスクルーシブ

排他モード`SRWLock`でオブジェクトを取得します。

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*ロック*<br/>
`SRWLock`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

排`SRWLock`他モードのオブジェクト。

## <a name="srwlocklockshared"></a><a name="lockshared"></a>SRWロック::ロックシェアード

共有モードで`SRWLock`オブジェクトを取得します。

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*ロック*<br/>
`SRWLock`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

共有`SRWLock`モードのオブジェクト。

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a>SRWロック::SRWロック

`SRWLock` クラスの新しいインスタンスを初期化します。

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a>SRWロック::SRWLock_

現在`SRWLock`のオブジェクトの基になるロック変数を格納します。

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a>SRWロック::トリロックエクスクルーシブ

現在のオブジェクトまたは指定`SRWLock`した`SRWLock`オブジェクトの排他モードでオブジェクトを取得しようとします。 呼び出しが成功すると、呼び出し元のスレッドはロックの所有権を取得します。

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*ロック*<br/>
`SRWLock`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した`SRWLock`場合、排他モードのオブジェクトと呼び出し元スレッドはロックの所有権を取得します。 それ以外の`SRWLock`場合は、状態が無効なオブジェクト。

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a>SRWロック::トライロックシェア

現在のオブジェクトまたは指定`SRWLock`した`SRWLock`オブジェクトの共有モードでオブジェクトを取得しようとします。

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*ロック*<br/>
`SRWLock`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合、`SRWLock`共有モードのオブジェクトと呼び出し元スレッドがロックの所有権を取得します。 それ以外の`SRWLock`場合は、状態が無効なオブジェクト。
