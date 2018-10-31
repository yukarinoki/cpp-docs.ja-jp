---
title: SRWLockSharedTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5cfebfd1a6ccb1f243b534c9693a4402de574f17
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48233678"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 構造体

一般的な特性について説明します、`SRWLock`共有ロック モードでのクラス。

## <a name="syntax"></a>構文

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | --------------------------------------------------------------------------
`Type` | ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラス。

### <a name="public-methods"></a>パブリック メソッド

名前                                                     | 説明
-------------------------------------------------------- | -----------------------------------------------------------------
[Srwlocksharedtraits::getinvalidvalue](#getinvalidvalue) | 取得、`SRWLockSharedTraits`オブジェクトは常に有効です。
[Srwlocksharedtraits::unlock](#unlock)                   | 指定したの排他的制御を解放`SRWLock`オブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLockSharedTraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Srwlocksharedtraits::getinvalidvalue

取得、`SRWLockSharedTraits`オブジェクトは常に有効です。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

識別するハンドルを`SRWLockSharedTraits`オブジェクト。

## <a name="unlock"></a>Srwlocksharedtraits::unlock

指定したの排他的制御を解放`SRWLock`オブジェクト。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*srwlock*<br/>
識別するハンドルを`SRWLock`オブジェクト。
