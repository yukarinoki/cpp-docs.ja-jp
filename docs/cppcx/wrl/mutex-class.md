---
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
ms.openlocfilehash: 36466bd00c5b100f20ee87173e68fdef4131ec23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371240"
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

### <a name="public-constructor"></a>パブリック コンストラクタ

名前                   | 説明
---------------------- | ------------------------------------------------
[ミューテックス::ミューテックス](#mutex) | `Mutex` クラスの新しいインスタンスを初期化します。

### <a name="public-members"></a>パブリックメンバー

名前                 | 説明
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[ミューテックス::ロック](#lock) | 現在のオブジェクト、または指定したハンドル`Mutex`に関連付けられたオブジェクトがミューテックスを解放するか、指定されたタイムアウト間隔が経過するまで待機します。

### <a name="public-operator"></a>公共オペレーター

名前                                 | 説明
------------------------------------ | ---------------------------------------------------------------------------
[ミューテックス::演算子=](#operator-assign) | 指定した`Mutex`オブジェクトを現在`Mutex`のオブジェクトに割り当てます (移動)。

## <a name="inheritance-hierarchy"></a>継承階層

`Mutex`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="mutexlock"></a><a name="lock"></a>ミューテックス::ロック

現在のオブジェクト、または指定したハンドル`Mutex`に関連付けられたオブジェクトがミューテックスを解放するか、指定されたタイムアウト間隔が経過するまで待機します。

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
`Mutex`オブジェクトのハンドル。

### <a name="return-value"></a>戻り値

## <a name="mutexmutex"></a><a name="mutex"></a>ミューテックス::ミューテックス

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

*H*<br/>
`Mutex`オブジェクトへのハンドル、またはハンドルへの右辺値参照。

### <a name="remarks"></a>解説

最初のコンストラクターは、指定`Mutex`したハンドルからオブジェクトを初期化します。 2 番目のコンストラクターは`Mutex`、指定したハンドルからオブジェクトを初期化し、ミューテックスの所有権を現在`Mutex`のオブジェクトに移動します。

## <a name="mutexoperator"></a><a name="operator-assign"></a>ミューテックス::演算子=

指定した`Mutex`オブジェクトを現在`Mutex`のオブジェクトに割り当てます (移動)。

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`Mutex`オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

現在`Mutex`のオブジェクトへの参照。

### <a name="remarks"></a>解説

詳細については、「[右辺値参照宣言子: &&」](../../cpp/rvalue-reference-declarator-amp-amp.md)の **「セマンティクスの移動**」セクションを参照してください。
