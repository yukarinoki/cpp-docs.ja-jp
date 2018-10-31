---
title: SRWLockExclusiveTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7737c802634b618b9ea363c231a44d9381ad30ae
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235166"
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

## <a name="requirements"></a>要件

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
