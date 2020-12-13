---
description: 詳細については、「SRWLockSharedTraits 構造」を参照してください。
title: SRWLockSharedTraits 構造体
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: 2cdfbd584adeffc9dedd8504d9183d6c5d4c1a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135123"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 構造体

共有ロックモードでのクラスの一般的な特性について説明し `SRWLock` ます。

## <a name="syntax"></a>構文

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | --------------------------------------------------------------------------
`Type` | [Srwlock](srwlock-class.md)クラスへのポインターのシノニム。

### <a name="public-methods"></a>パブリック メソッド

名前                                                     | 説明
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits:: GetInvalidValue](#getinvalidvalue) | `SRWLockSharedTraits`常に無効なオブジェクトを取得します。
[SRWLockSharedTraits:: Unlock](#unlock)                   | 指定されたオブジェクトの排他的な制御を解放 `SRWLock` します。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLockSharedTraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper:: HandleTraits

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockSharedTraits:: GetInvalidValue

`SRWLockSharedTraits`常に無効なオブジェクトを取得します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

オブジェクトへのハンドル `SRWLockSharedTraits` 。

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a> SRWLockSharedTraits:: Unlock

指定されたオブジェクトの排他的な制御を解放 `SRWLock` します。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*srwlock*<br/>
オブジェクトへのハンドル `SRWLock` 。
