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
ms.openlocfilehash: 52c4404fa28f680a9a7a4592d03f535e8406d1a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374280"
---
# <a name="synclockt-class"></a>SyncLockT クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>パラメーター

*同期トレイト*<br/>
リソースの所有権を取得できる型。

## <a name="remarks"></a>解説

リソースの排他的または共有所有権を取得できる型を表します。

この`SyncLockT`クラスは[、SRWLock](srwlock-class.md)クラスの実装を支援するために使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                      | 説明
----------------------------------------- | ----------------------------------------------------
[シンクロック::シンクロック](#synclockt)        | `SyncLockT` クラスの新しいインスタンスを初期化します。
[シンクロック::~シンクロック](#tilde-synclockt) | クラスのインスタンスを初期化解除します`SyncLockT`。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                               | 説明
---------------------------------- | ----------------------------------------------------
[シンクロック::シンクロック](#synclockt) | `SyncLockT` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                             | 説明
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[シンクロック::イズロック](#islocked) | 現在`SyncLockT`のオブジェクトがリソースを所有しているかどうかを示します。つまり、オブジェクトは`SyncLockT`*ロックされています*。
[シンクロック::ロック解除](#unlock)     | 現在`SyncLockT`のオブジェクトが保持しているリソースの制御を解放します (存在する場合)。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                      | 説明
------------------------- | -------------------------------------------------------------------
[シンクロック::sync_](#sync) | クラスで表される基になるリソース`SyncLockT`を保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`SyncLockT`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::D

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a>シンクロック::~シンクロック

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
~SyncLockT();
```

### <a name="remarks"></a>解説

クラスのインスタンスを初期化解除します`SyncLockT`。

このデストラクターは、現在`SyncLockT`のインスタンスのロックも解除します。

## <a name="synclocktislocked"></a><a name="islocked"></a>シンクロック::イズロック

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>戻り値

オブジェクトがロック`SyncLockT`されている場合は true、ロックされている場合は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

現在`SyncLockT`のオブジェクトがリソースを所有しているかどうかを示します。つまり、オブジェクトは`SyncLockT`*ロックされています*。

## <a name="synclocktsync_"></a><a name="sync"></a>シンクロック::sync_

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>解説

クラスで表される基になるリソース`SyncLockT`を保持します。

## <a name="synclocktsynclockt"></a><a name="synclockt"></a>シンクロック::シンクロック

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別`SyncLockT`のオブジェクトへの右辺値参照。

*同期*<br/>
別`SyncLockWithStatusT`のオブジェクトへの参照。

### <a name="remarks"></a>解説

`SyncLockT` クラスの新しいインスタンスを初期化します。

最初のコンストラクターは、パラメーター `SyncLockT` other で`SyncLockT`指定された別の*other*オブジェクトから現在のオブジェクトを初期化し、`SyncLockT`その後、そのオブジェクトを無効にします。 2 番目の`protected`コンストラクターは で、現在`SyncLockT`のオブジェクトを無効な状態に初期化します。

## <a name="synclocktunlock"></a><a name="unlock"></a>シンクロック::ロック解除

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
void Unlock();
```

### <a name="remarks"></a>解説

現在`SyncLockT`のオブジェクトが保持しているリソースの制御を解放します (存在する場合)。
