---
title: max_variable_size クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
ms.openlocfilehash: 79e37d8c464a009e4a5196aeacc8d4a718e355b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370962"
---
# <a name="max_variable_size-class"></a>max_variable_size クラス

割り当てたメモリ ブロックの数にほぼ比例した最長値までに [freelist](../standard-library/freelist-class.md) オブジェクトを制御する、[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
class max_variable_size
```

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[max_variable_size](#max_variable_size)|`max_variable_size` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocated](#allocated)|割り当てられたメモリ ブロックの数を増やします。|
|[解放](#deallocated)|割り当てられたメモリ ブロックの数を減らします。|
|[完全](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|
|[リリース](#released)|フリー リスト上のメモリ ブロックの数を減らします。|
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="max_variable_sizeallocated"></a><a name="allocated"></a>max_variable_size::割り当て済み

割り当てられたメモリ ブロックの数を増やします。

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

このメンバー関数は *_Nx*、格納されている値`_Nallocs`に_Nxを追加します。 このメンバー関数は、オペレーター **new**を`cache_freelist::allocate`呼び出した後に呼び出されます。 引数 *_Nx*は、演算子**new**によって割り当てられたチャンク内のメモリ ブロックの数です。

## <a name="max_variable_sizedeallocated"></a><a name="deallocated"></a>max_variable_size::d割り当て済み

割り当てられたメモリ ブロックの数を減らします。

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

メンバー関数は、格納 *_Nx*された値`_Nallocs`から_Nxを減算します。 このメンバー関数は、オペレーター delete`cache_freelist::deallocate`を呼び出すたびに呼び出**されます**。 引数 *_Nx*は、演算子 delete によって割り当て解除されたチャンク内のメモリ ブロックの数**です**。

## <a name="max_variable_sizefull"></a><a name="full"></a>max_variable_size::フル

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

**true** `_Nallocs / 16 + 16 <= _Nblocks`の場合は、

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出し**true**が`deallocate`true を返す場合は、メモリ ブロックを空きリストに配置します。false を返す`deallocate`場合は、演算子**delete**を呼び出してブロックの割り当てを解除します。

## <a name="max_variable_sizemax_variable_size"></a><a name="max_variable_size"></a>max_variable_size::max_variable_size

`max_variable_size` 型のオブジェクトを構築します。

```cpp
max_variable_size();
```

### <a name="remarks"></a>解説

このコンストラクターは、格納された値 `_Nblocks` および `_Nallocs` をゼロに初期化します。

## <a name="max_variable_sizereleased"></a><a name="released"></a>max_variable_size::リリース済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納された値 `_Nblocks` を減らします。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。

## <a name="max_variable_sizesaved"></a><a name="saved"></a>max_variable_size::保存済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納された値 `_Nblocks` を増やします。 このメンバー関数は、`cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
