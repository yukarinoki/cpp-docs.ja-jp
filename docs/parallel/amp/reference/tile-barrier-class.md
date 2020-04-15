---
title: tile_barrier クラス
ms.date: 03/27/2019
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
ms.openlocfilehash: c00f1e41e70e723be185959eeff176390def7647
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374727"
---
# <a name="tile_barrier-class"></a>tile_barrier クラス

`wait` メソッドを使用してスレッド グループ (タイル) で実行されているスレッドの実行を同期します。 ランタイムのみがこのクラスをインスタンス化できます。

## <a name="syntax"></a>構文

```cpp
class tile_barrier;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[tile_barrierコンストラクタ](#ctor)|`tile_barrier` クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[待つ](#wait)|タイルのすべてのスレッドの待機が完了するまで、スレッド グループ (タイル) のすべてのスレッドの実行を停止するように指示します。|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|すべてのメモリ アクセスが完了し、タイルのすべてのスレッドがこの呼び出しに到達するまで、タイルのすべてのスレッドの実行をブロックします。|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|すべてのグローバル メモリ アクセスが完了し、タイルのすべてのスレッドがこの呼び出しに到達するまで、タイルのすべてのスレッドの実行をブロックします。|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|すべての `tile_static` メモリ アクセスが完了し、タイルのすべてのスレッドがこの呼び出しに到達するまで、タイルのすべてのスレッドの実行をブロックします。|

## <a name="inheritance-hierarchy"></a>継承階層

`tile_barrier`

## <a name="requirements"></a>必要条件

**ヘッダー:** amp.h

**名前空間:** Concurrency

## <a name="tile_barrier-constructor"></a><a name="ctor"></a>tile_barrierコンストラクタ

既存のインスタンスをコピーして、クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピーする `tile_barrier` オブジェクトです。

## <a name="wait"></a>wait

スレッド グループ (タイル) 内のすべてのスレッドに、タイル内のすべてのスレッドが待機を終了するまで実行を停止するように指示します。

### <a name="syntax"></a>構文

```cpp
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a><a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence

タイルのすべてのスレッドがこの呼び出しに到達するまで、タイルのすべてのスレッドの実行をブロックします。 これによって、すべてのメモリ アクセスがスレッド タイルの他のスレッドから参照でき、プログラムの順序で実行されます。

### <a name="syntax"></a>構文

```cpp
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="a-namewait_with_global_memory_fence-wait_with_global_memory_fence"></a><a name="wait_with_global_memory_fence">wait_with_global_memory_fence

タイルのすべてのスレッドがこの呼び出しに到達するまで、タイルのすべてのスレッドの実行をブロックします。 これによって、すべてのグローバル メモリ アクセスがスレッド タイルの他のスレッドから参照でき、プログラムの順序で実行されます。

### <a name="syntax"></a>構文

```cpp
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="a-namewait_with_tile_static_memory_fence-wait_with_tile_static_memory_fence"></a><a name="wait_with_tile_static_memory_fence">wait_with_tile_static_memory_fence

タイルのすべてのスレッドがこの呼び出しに到達するまで、タイルのすべてのスレッドの実行をブロックします。 これにより、メモリ`tile_static`アクセスがスレッド タイル内の他のスレッドから参照でき、プログラム順に実行されます。

### <a name="syntax"></a>構文

```cpp
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>関連項目

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
