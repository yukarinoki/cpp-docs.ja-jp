---
description: '詳細については、次を参照してください: SRWLockExclusiveTraits 構造体'
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
ms.openlocfilehash: 135d4f866d1ca32ee9170ef9844cb0bf8d38c29a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186208"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 構造体

排他ロックモードでのクラスの一般的な特性について説明し `SRWLock` ます。

## <a name="syntax"></a>構文

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | --------------------------------------------------------------------------
`Type` | [Srwlock](srwlock-class.md)クラスへのポインターのシノニム。

### <a name="public-methods"></a>パブリック メソッド

名前                                                        | 説明
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits:: GetInvalidValue](#getinvalidvalue) | `SRWLockExclusiveTraits`常に無効なオブジェクトを取得します。
[SRWLockExclusiveTraits:: Unlock](#unlock)                   | 指定されたオブジェクトの排他的な制御を解放 `SRWLock` します。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLockExclusiveTraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockExclusiveTraits:: GetInvalidValue

`SRWLockExclusiveTraits`常に無効なオブジェクトを取得します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

空の `SRWLockExclusiveTraits` オブジェクトです。

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a> SRWLockExclusiveTraits:: Unlock

指定されたオブジェクトの排他的な制御を解放 `SRWLock` します。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*srwlock*<br/>
オブジェクトをハンドル `SRWLock` します。
