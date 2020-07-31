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
ms.openlocfilehash: b95e512f89ee1ff32ca9f1bea51bce643d185a2e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220523"
---
# <a name="criticalsection-class"></a>CriticalSection クラス

クリティカルセクションオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class CriticalSection;
```

## <a name="members"></a>メンバー

### <a name="constructor"></a>コンストラクター

名前                                                        | 説明
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[CriticalSection:: CriticalSection](#criticalsection)        | Mutex オブジェクトに似た同期オブジェクトを初期化しますが、1つのプロセスのスレッドだけが使用できます。
[CriticalSection:: ~ CriticalSection](#tilde-criticalsection) | 現在のオブジェクトを初期化して破棄し `CriticalSection` ます。

### <a name="public-methods"></a>パブリック メソッド

名前                                 | 説明
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[CriticalSection:: IsValid](#isvalid) | 現在のクリティカルセクションが有効かどうかを示します。
[CriticalSection:: Lock](#lock)       | 指定したクリティカルセクションオブジェクトの所有権を待機します。 関数は、呼び出し元のスレッドに所有権が付与されると、を返します。
[CriticalSection:: TryLock](#trylock) | ブロックせずにクリティカルセクションを入力しようとします。 呼び出しが成功すると、呼び出し元のスレッドはクリティカルセクションの所有権を取得します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------
[CriticalSection:: cs_](#cs) | クリティカルセクションのデータメンバーを宣言します。

## <a name="inheritance-hierarchy"></a>継承階層

`CriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a>CriticalSection:: ~ CriticalSection

現在のオブジェクトを初期化して破棄し `CriticalSection` ます。

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a>CriticalSection:: CriticalSection

Mutex オブジェクトに似た同期オブジェクトを初期化しますが、1つのプロセスのスレッドだけが使用できます。

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>パラメーター

*spincount*<br/>
クリティカルセクションオブジェクトのスピンカウント。 既定値は 0 です。

### <a name="remarks"></a>解説

クリティカルセクションと spincounts の詳細については、 `InitializeCriticalSectionAndSpinCount` `Synchronization` Windows API ドキュメントの「」セクションの関数を参照してください。

## <a name="criticalsectioncs_"></a><a name="cs"></a>CriticalSection:: cs_

クリティカルセクションのデータメンバーを宣言します。

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>解説

このデータメンバーは保護されています。

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a>CriticalSection:: IsValid

現在のクリティカルセクションが有効かどうかを示します。

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>戻り値

既定では、は常にを返し **`true`** ます。

## <a name="criticalsectionlock"></a><a name="lock"></a>CriticalSection:: Lock

指定したクリティカルセクションオブジェクトの所有権を待機します。 関数は、呼び出し元のスレッドに所有権が付与されると、を返します。

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>パラメーター

*同時*<br/>
ユーザーが指定したクリティカルセクションオブジェクト。

### <a name="return-value"></a>戻り値

現在のクリティカルセクションのロックを解除するために使用できるロックオブジェクト。

### <a name="remarks"></a>解説

最初の `Lock` 関数は、現在のクリティカルセクションオブジェクトに影響します。 2番目の関数は、 `Lock` ユーザーが指定したクリティカルセクションに影響します。

## <a name="criticalsectiontrylock"></a><a name="trylock"></a>CriticalSection:: TryLock

ブロックせずにクリティカルセクションを入力しようとします。 呼び出しが成功すると、呼び出し元のスレッドはクリティカルセクションの所有権を取得します。

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>パラメーター

*同時*<br/>
ユーザーが指定したクリティカルセクションオブジェクト。

### <a name="return-value"></a>戻り値

クリティカルセクションが正常に入力された場合、または現在のスレッドがクリティカルセクションを既に所有している場合は、0以外の値。 別のスレッドがクリティカルセクションを既に所有している場合は0。

### <a name="remarks"></a>解説

最初の `TryLock` 関数は、現在のクリティカルセクションオブジェクトに影響します。 2番目の関数は、 `TryLock` ユーザーが指定したクリティカルセクションに影響します。
