---
title: CriticalSection クラス
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: 5deb89e795d1886ca316886ae1ea260ce1f36fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372585"
---
# <a name="criticalsection-class"></a>CriticalSection クラス

クリティカル セクション オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class CriticalSection;
```

## <a name="members"></a>メンバー

### <a name="constructor"></a>Constructor

名前                                                        | 説明
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[クリティカルセクション::クリティカルセクション](#criticalsection)        | ミューテックス オブジェクトに似ていますが、単一のプロセスのスレッドのみが使用できる同期オブジェクトを初期化します。
[クリティカルセクション::~クリティカルセクション](#tilde-criticalsection) | 現在`CriticalSection`のオブジェクトを初期化解除し、破棄します。

### <a name="public-methods"></a>パブリック メソッド

名前                                 | 説明
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[クリティカルセクション::IsValid](#isvalid) | 現在のクリティカル セクションが有効かどうかを示します。
[クリティカルセクション::ロック](#lock)       | 指定したクリティカル セクション オブジェクトの所有権を待機します。 呼び出し元のスレッドに所有権が付与されると、関数は戻ります。
[クリティカルセクション::トライロック](#trylock) | ブロックせずにクリティカル セクションに入ろうとします。 呼び出しが成功すると、呼び出し元スレッドはクリティカル セクションの所有権を取得します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------
[クリティカルセクション::cs_](#cs) | クリティカル セクション データ メンバーを宣言します。

## <a name="inheritance-hierarchy"></a>継承階層

`CriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a>クリティカルセクション::~クリティカルセクション

現在`CriticalSection`のオブジェクトを初期化解除し、破棄します。

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a>クリティカルセクション::クリティカルセクション

ミューテックス オブジェクトに似ていますが、単一のプロセスのスレッドのみが使用できる同期オブジェクトを初期化します。

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>パラメーター

*スピンカウント*<br/>
クリティカル セクション オブジェクトのスピン カウント。 既定値は 0 です。

### <a name="remarks"></a>解説

クリティカル セクションとスピンカウントの詳細については、Windows `InitializeCriticalSectionAndSpinCount` API の`Synchronization`ドキュメネーションのセクションの関数を参照してください。

## <a name="criticalsectioncs_"></a><a name="cs"></a>クリティカルセクション::cs_

クリティカル セクション データ メンバーを宣言します。

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>解説

このデータ メンバーは保護されています。

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a>クリティカルセクション::IsValid

現在のクリティカル セクションが有効かどうかを示します。

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>戻り値

既定では、常に**true を**返します。

## <a name="criticalsectionlock"></a><a name="lock"></a>クリティカルセクション::ロック

指定したクリティカル セクション オブジェクトの所有権を待機します。 呼び出し元のスレッドに所有権が付与されると、関数は戻ります。

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>パラメーター

*cs*<br/>
ユーザー指定のクリティカル セクション オブジェクト。

### <a name="return-value"></a>戻り値

現在のクリティカル セクションのロックを解除するために使用できるロック オブジェクト。

### <a name="remarks"></a>解説

最初`Lock`の関数は、現在のクリティカル セクション オブジェクトに影響します。 2`Lock`番目の関数は、ユーザー指定のクリティカル セクションに影響します。

## <a name="criticalsectiontrylock"></a><a name="trylock"></a>クリティカルセクション::トライロック

ブロックせずにクリティカル セクションに入ろうとします。 呼び出しが成功すると、呼び出し元スレッドはクリティカル セクションの所有権を取得します。

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>パラメーター

*cs*<br/>
ユーザー指定のクリティカル セクション オブジェクト。

### <a name="return-value"></a>戻り値

クリティカル セクションが正常に入力された場合、または現在のスレッドが既にクリティカル セクションを所有している場合は、0 以外の値。 別のスレッドが既にクリティカル セクションを所有している場合は 0。

### <a name="remarks"></a>解説

最初`TryLock`の関数は、現在のクリティカル セクション オブジェクトに影響します。 2`TryLock`番目の関数は、ユーザー指定のクリティカル セクションに影響します。
