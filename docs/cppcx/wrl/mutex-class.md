---
description: '詳細: Mutex クラス'
title: Mutex クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: f69c14014a2283fe56ef8e7f705bebe5a5f6dc9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330838"
---
# <a name="mutex-class"></a>Mutex クラス

共有リソースを排他的に制御する同期オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前       | 説明
---------- | ------------------------------------------------------
`SyncLock` | 同期ロックをサポートするクラスのシノニム。

### <a name="public-constructor"></a>パブリックコンストラクター

名前                   | 説明
---------------------- | ------------------------------------------------
[Mutex:: Mutex](#mutex) | `Mutex` クラスの新しいインスタンスを初期化します。

### <a name="public-members"></a>パブリックメンバー

名前                 | 説明
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex:: Lock](#lock) | 現在のオブジェクト、または `Mutex` 指定されたハンドルに関連付けられているオブジェクトがミューテックスを解放するか、指定されたタイムアウト間隔が経過するまで待機します。

### <a name="public-operator"></a>Public 演算子

名前                                 | 説明
------------------------------------ | ---------------------------------------------------------------------------
[Mutex:: operator =](#operator-assign) | 指定された `Mutex` オブジェクトを現在のオブジェクトに割り当てます (移動し `Mutex` ます)。

## <a name="inheritance-hierarchy"></a>継承階層

`Mutex`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="mutexlock"></a><a name="lock"></a> Mutex:: Lock

現在のオブジェクト、または `Mutex` 指定されたハンドルに関連付けられているオブジェクトがミューテックスを解放するか、指定されたタイムアウト間隔が経過するまで待機します。

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

*milliseconds*<br/>
タイムアウト間隔 (ミリ秒単位)。 既定値は無限で、無制限に待機します。

*h*<br/>
オブジェクトのハンドル `Mutex` 。

### <a name="return-value"></a>戻り値

## <a name="mutexmutex"></a><a name="mutex"></a> Mutex:: Mutex

`Mutex` クラスの新しいインスタンスを初期化します。

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
オブジェクトへのハンドル、またはハンドルへの右辺値参照 `Mutex` 。

### <a name="remarks"></a>解説

最初のコンストラクターは、 `Mutex` 指定されたハンドルからオブジェクトを初期化します。 2番目のコンストラクターは、 `Mutex` 指定されたハンドルからオブジェクトを初期化し、ミューテックスの所有権を現在のオブジェクトに移動し `Mutex` ます。

## <a name="mutexoperator"></a><a name="operator-assign"></a> Mutex:: operator =

指定された `Mutex` オブジェクトを現在のオブジェクトに割り当てます (移動し `Mutex` ます)。

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
オブジェクトへの右辺値参照 `Mutex` 。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照 `Mutex` 。

### <a name="remarks"></a>解説

詳細については、「[右辺値参照宣言子:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md)」の「**移動セマンティクス**」セクションを参照してください。
