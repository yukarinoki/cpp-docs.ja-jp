---
title: SRWLockExclusiveTraits 構造体
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: 4005f0dc1f75b79650963efc9a6f9f7522bc3395
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476467"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 構造体

一般的な特性について説明します、`SRWLock`排他ロック モードでのクラス。

## <a name="syntax"></a>構文

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | --------------------------------------------------------------------------
`Type` | ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラス。

### <a name="public-methods"></a>パブリック メソッド

名前                                                        | 説明
----------------------------------------------------------- | --------------------------------------------------------------------
[Srwlockexclusivetraits::getinvalidvalue](#getinvalidvalue) | 取得、`SRWLockExclusiveTraits`オブジェクトは常に有効です。
[Srwlockexclusivetraits::unlock](#unlock)                   | 指定したの排他的制御を解放`SRWLock`オブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLockExclusiveTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Srwlockexclusivetraits::getinvalidvalue

取得、`SRWLockExclusiveTraits`オブジェクトは常に有効です。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

空の `SRWLockExclusiveTraits` オブジェクト。

## <a name="unlock"></a>Srwlockexclusivetraits::unlock

指定したの排他的制御を解放`SRWLock`オブジェクト。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*srwlock*<br/>
ハンドル、`SRWLock`オブジェクト。
