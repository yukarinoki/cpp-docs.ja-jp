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
ms.openlocfilehash: eb7b30915d6061e8470601df33fecec310d1bbca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374306"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 構造体

排他ロック モードで`SRWLock`のクラスの一般的な特性について説明します。

## <a name="syntax"></a>構文

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前   | 説明
------ | --------------------------------------------------------------------------
`Type` | [SRWLOCK](srwlock-class.md)クラスへのポインターの同義語。

### <a name="public-methods"></a>パブリック メソッド

名前                                                        | 説明
----------------------------------------------------------- | --------------------------------------------------------------------
[リクルーシブトレイト::無効な値を取得します。](#getinvalidvalue) | 常に無効`SRWLockExclusiveTraits`なオブジェクトを取得します。
[SRWロックエクスクルーシブトレイト::ロック解除](#unlock)                   | 指定した`SRWLock`オブジェクトの排他制御を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`SRWLockExclusiveTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::ハンドルトレイツ

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>リクルーシブトレイト::無効な値を取得します。

常に無効`SRWLockExclusiveTraits`なオブジェクトを取得します。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>戻り値

空の `SRWLockExclusiveTraits` オブジェクトです。

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a>SRWロックエクスクルーシブトレイト::ロック解除

指定した`SRWLock`オブジェクトの排他制御を解放します。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*スヴロック*<br/>
`SRWLock`オブジェクトへのハンドル。
