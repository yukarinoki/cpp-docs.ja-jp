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
ms.openlocfilehash: 53d2603c82e94710ed687dce4caeec24aeb2f60a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561649"
---
# <a name="max_variable_size-class"></a>max_variable_size クラス

割り当てたメモリ ブロックの数にほぼ比例した最長値までに [freelist](../standard-library/freelist-class.md) オブジェクトを制御する、[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
class max_variable_size
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[max_variable_size](#max_variable_size)|`max_variable_size` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocated](#allocated)|割り当てられたメモリ ブロックの数を増やします。|
|[解放](#deallocated)|割り当てられたメモリ ブロックの数を減らします。|
|[full](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|
|[たら](#released)|フリー リスト上のメモリ ブロックの数を減らします。|
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="max_variable_sizeallocated"></a><a name="allocated"></a> max_variable_size:: 割り当て済み

割り当てられたメモリ ブロックの数を増やします。

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

*_Nx*\
増分値。

### <a name="remarks"></a>解説

このメンバー関数は、格納されている値に *_Nx* を追加し `_Nallocs` ます。 このメンバー関数は、to 演算子による呼び出しが成功するたびに呼び出され `cache_freelist::allocate` **`new`** ます。 引数 *_Nx* は、演算子によって割り当てられたチャンク内のメモリブロックの数です **`new`** 。

## <a name="max_variable_sizedeallocated"></a><a name="deallocated"></a> max_variable_size::d eallocated

割り当てられたメモリ ブロックの数を減らします。

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

*_Nx*\
増分値。

### <a name="remarks"></a>解説

このメンバー関数は、格納されている値から *_Nx* を減算し `_Nallocs` ます。 このメンバー関数は、to 演算子による各呼び出しの後に呼び出され `cache_freelist::deallocate` **`delete`** ます。 引数 *_Nx* は、演算子によって割り当て解除されたチャンク内のメモリブロックの数です **`delete`** 。

## <a name="max_variable_sizefull"></a><a name="full"></a> max_variable_size:: full

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

**`true`**`_Nallocs / 16 + 16 <= _Nblocks`の場合。

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出しでが返された場合 **`true`** 、は `deallocate` メモリブロックをフリーリストに格納します。 false を返す場合は、 `deallocate` 演算子を呼び出して **`delete`** ブロックの割り当てを解除します。

## <a name="max_variable_sizemax_variable_size"></a><a name="max_variable_size"></a> max_variable_size:: max_variable_size

`max_variable_size` 型のオブジェクトを構築します。

```cpp
max_variable_size();
```

### <a name="remarks"></a>解説

このコンストラクターは、格納された値 `_Nblocks` および `_Nallocs` をゼロに初期化します。

## <a name="max_variable_sizereleased"></a><a name="released"></a> max_variable_size:: 解放されました

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納された値 `_Nblocks` を減らします。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。

## <a name="max_variable_sizesaved"></a><a name="saved"></a> max_variable_size:: saved

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納された値 `_Nblocks` を増やします。 このメンバー関数は、`cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
