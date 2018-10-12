---
title: CriticalSection クラス |Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4b543d3436f04d1a8aaa92647449854831002a6
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162374"
---
# <a name="criticalsection-class"></a>CriticalSection クラス

クリティカル セクション オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class CriticalSection;
```

## <a name="members"></a>メンバー

### <a name="constructor"></a>コンストラクター

名前                                                        | 説明
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Criticalsection::criticalsection](#criticalsection)        | ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。
[CriticalSection:: ~ CriticalSection](#tilde-criticalsection) | 初期化を解除し、現在の破棄`CriticalSection`オブジェクト。

### <a name="public-methods"></a>パブリック メソッド

名前                                 | 説明
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[Criticalsection::isvalid](#isvalid) | 現在の重要なセクションが有効かどうかを示します。
[Criticalsection::lock](#lock)       | 指定されたクリティカル セクション オブジェクトの所有権を待機します。 呼び出し元のスレッドの所有権が付与されると、関数を返します。
[Criticalsection::trylock](#trylock) | ブロックすることがなく、クリティカル セクションを入力しようとします。 呼び出しが成功した場合、呼び出し元のスレッドはクリティカル セクションの所有権を取得します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------
[Criticalsection::cs _](#cs) | クリティカル セクションのデータ メンバーを宣言します。

## <a name="inheritance-hierarchy"></a>継承階層

`CriticalSection`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="tilde-criticalsection"></a>CriticalSection:: ~ CriticalSection

初期化を解除し、現在の破棄`CriticalSection`オブジェクト。

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsection"></a>Criticalsection::criticalsection

ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>パラメーター

*spincount*<br/>
クリティカル セクション オブジェクトのスピン カウントします。 既定値は 0 です。

### <a name="remarks"></a>Remarks

クリティカル セクションと spincounts の詳細については、次を参照してください。、`InitializeCriticalSectionAndSpinCount`で機能、 `Synchronization` Windows API のドキュメントのセクション。

## <a name="cs"></a>Criticalsection::cs _

クリティカル セクションのデータ メンバーを宣言します。

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Remarks

このデータ メンバーは保護されます。

## <a name="isvalid"></a>Criticalsection::isvalid

現在の重要なセクションが有効かどうかを示します。

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>戻り値

既定では、常に返します**true**します。

## <a name="lock"></a>Criticalsection::lock

指定されたクリティカル セクション オブジェクトの所有権を待機します。 呼び出し元のスレッドの所有権が付与されると、関数を返します。

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

現在の重要なセクションのロック解除に使用できるロック オブジェクト。

### <a name="remarks"></a>Remarks

最初の`Lock`関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目の`Lock`関数、ユーザー指定のクリティカル セクションに影響を与えます。

## <a name="trylock"></a>Criticalsection::trylock

ブロックすることがなく、クリティカル セクションを入力しようとします。 呼び出しが成功した場合、呼び出し元のスレッドはクリティカル セクションの所有権を取得します。

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

クリティカル セクションが正しく入力された場合は 0 以外の値または現在のスレッドはクリティカル セクションを既に所有しています。 別のスレッドがクリティカル セクション既に所有している場合は 0 します。

### <a name="remarks"></a>Remarks

最初の`TryLock`関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目の`TryLock`関数、ユーザー指定のクリティカル セクションに影響を与えます。
