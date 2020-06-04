---
title: Semaphore クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: e017b1b6316c4b6d49563d9a543950ab28961d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359354"
---
# <a name="semaphore-class"></a>Semaphore クラス

限られた数のユーザーをサポートできる共有リソースを制御する同期オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前       | 説明
---------- | ------------------------------------------------------
`SyncLock` | 同期ロックをサポートするクラスのシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | ----------------------------------------------------
[セマフォ::セマフォ](#semaphore) | `Semaphore` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                     | 説明
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[セマフォ::ロック](#lock) | 現在のオブジェクト、または指定したハンドルに関連付けられたオブジェクトがシグナル状態になるまで待機するか、指定されたタイムアウト間隔が経過するまで待機します。

### <a name="public-operators"></a>パブリック演算子

名前                                     | 説明
---------------------------------------- | ---------------------------------------------------------------------------------------
[セマフォ::演算子=](#operator-assign) | 指定したハンドルをオブジェクトから`Semaphore`現在`Semaphore`のオブジェクトに移動します。

## <a name="inheritance-hierarchy"></a>継承階層

`Semaphore`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="semaphorelock"></a><a name="lock"></a>セマフォ::ロック

現在のオブジェクト、または指定したハンドル`Semaphore`に関連付けられたオブジェクトがシグナル状態になるまで待機するか、指定されたタイムアウト間隔が経過するまで待機します。

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>パラメーター

*ミリ秒*<br/>
タイムアウト間隔 (ミリ秒単位)。 デフォルト値は無限で、無期限に待機します。

*H*<br/>
`Semaphore`オブジェクトへのハンドル。

### <a name="return-value"></a>戻り値

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>` 変数

## <a name="semaphoreoperator"></a><a name="operator-assign"></a>セマフォ::演算子=

指定したハンドルをオブジェクトから`Semaphore`現在`Semaphore`のオブジェクトに移動します。

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`Semaphore`オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

現在`Semaphore`のオブジェクトへの参照。

## <a name="semaphoresemaphore"></a><a name="semaphore"></a>セマフォ::セマフォ

`Semaphore` クラスの新しいインスタンスを初期化します。

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`Semaphore`オブジェクトへのハンドルまたは右辺値参照。
