---
title: SyncLockT クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
ms.openlocfilehash: 6a6e176020624f02e778ba5684a374abfbafa9e4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184671"
---
# <a name="synclockt-class"></a>SyncLockT クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>パラメーター

*SyncTraits*<br/>
リソースの所有権を取得できる型。

## <a name="remarks"></a>解説

リソースの排他的な所有権を取得できる型を表します。

たとえば、クラスは、 `SyncLockT` [Srwlock](srwlock-class.md)クラスを実装するために使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                      | 説明
----------------------------------------- | ----------------------------------------------------
[SyncLockT:: SyncLockT](#synclockt)        | `SyncLockT` クラスの新しいインスタンスを初期化します。
[SyncLockT:: ~ SyncLockT](#tilde-synclockt) | クラスのインスタンスを初期化解除 `SyncLockT` します。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                               | 説明
---------------------------------- | ----------------------------------------------------
[SyncLockT:: SyncLockT](#synclockt) | `SyncLockT` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                             | 説明
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT:: IsLocked](#islocked) | 現在のオブジェクトがリソースを所有しているかどうか、 `SyncLockT` つまり、 `SyncLockT` オブジェクトが*ロック*されているかどうかを示します。
[SyncLockT:: Unlock](#unlock)     | 現在のオブジェクトによって保持されているリソースの制御 `SyncLockT` を解放します (存在する場合)。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                      | 説明
------------------------- | -------------------------------------------------------------------
[SyncLockT:: sync_](#sync) | クラスによって表される基になるリソースを保持し `SyncLockT` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`SyncLockT`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper::D etails

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a>SyncLockT:: ~ SyncLockT

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
~SyncLockT();
```

### <a name="remarks"></a>解説

クラスのインスタンスを初期化解除 `SyncLockT` します。

このデストラクターも現在のインスタンスのロックを解除 `SyncLockT` します。

## <a name="synclocktislocked"></a><a name="islocked"></a>SyncLockT:: IsLocked

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>戻り値

**`true`**`SyncLockT`オブジェクトがロックされている場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

現在のオブジェクトがリソースを所有しているかどうか、 `SyncLockT` つまり、 `SyncLockT` オブジェクトが*ロック*されているかどうかを示します。

## <a name="synclocktsync_"></a><a name="sync"></a>SyncLockT:: sync_

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>解説

クラスによって表される基になるリソースを保持し `SyncLockT` ます。

## <a name="synclocktsynclockt"></a><a name="synclockt"></a>SyncLockT:: SyncLockT

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別のオブジェクトへの右辺値参照 `SyncLockT` 。

*頻度*<br/>
別のオブジェクトへの参照 `SyncLockWithStatusT` 。

### <a name="remarks"></a>解説

`SyncLockT` クラスの新しいインスタンスを初期化します。

最初のコンストラクターは、 `SyncLockT` `SyncLockT` *他の*パラメーターによって指定された別のオブジェクトから現在のオブジェクトを初期化し、もう一方のオブジェクトを無効にし `SyncLockT` ます。 2番目のコンストラクターは **`protected`** で、現在の `SyncLockT` オブジェクトを無効な状態に初期化します。

## <a name="synclocktunlock"></a><a name="unlock"></a>SyncLockT:: Unlock

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
void Unlock();
```

### <a name="remarks"></a>解説

現在のオブジェクトによって保持されているリソースの制御 `SyncLockT` を解放します (存在する場合)。
