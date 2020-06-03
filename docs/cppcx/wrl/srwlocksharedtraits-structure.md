---
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
ms.openlocfilehash: 0dc43d4b9c16145ed7a5abe03cddb598c59b1e94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374301"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 構造体

共有ロック モードでの`SRWLock`クラスの一般的な特性について説明します。

## <a name="syntax"></a>構文

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | --------------------------------------------------------------------------
`Type` | [SRWLOCK](srwlock-class.md)クラスへのポインターの同義語。

### <a name="public-methods"></a>パブリック メソッド

名前                                                     | 説明
-------------------------------------------------------- | -----------------------------------------------------------------
[ストリューロック共有トレイト::無効な値を取得します。](#getinvalidvalue) | 常に無効`SRWLockSharedTraits`なオブジェクトを取得します。
[SRWロックシェアードトレイツ::ロック解除](#unlock)                   | 指定した`SRWLock`オブジェクトの排他制御を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLockSharedTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>ストリューロック共有トレイト::無効な値を取得します。

常に無効`SRWLockSharedTraits`なオブジェクトを取得します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

`SRWLockSharedTraits`オブジェクトへのハンドル。

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a>SRWロックシェアードトレイツ::ロック解除

指定した`SRWLock`オブジェクトの排他制御を解放します。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*スヴロック*<br/>
`SRWLock`オブジェクトへのハンドル。
