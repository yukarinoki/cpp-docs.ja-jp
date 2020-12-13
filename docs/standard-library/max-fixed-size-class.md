---
description: '詳細情報: max_fixed_size クラス'
title: max_fixed_size クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
ms.openlocfilehash: 3238013547078640af42914fa21dddec622a9973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149280"
---
# <a name="max_fixed_size-class"></a>max_fixed_size クラス

[freelist](../standard-library/freelist-class.md) オブジェクトを固定の最長値までに制限する[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>パラメーター

*制限*\
`freelist` に格納する要素の最大数を決定する、最大クラス。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[max_fixed_size](#max_fixed_size)|`max_fixed_size` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocated](#allocated)|割り当てられたメモリ ブロックの数を増やします。|
|[解放](#deallocated)|割り当てられたメモリ ブロックの数を減らします。|
|[full](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|
|[たら](#released)|フリー リスト上のメモリ ブロックの数を減らします。|
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="max_fixed_sizeallocated"></a><a name="allocated"></a> max_fixed_size:: 割り当て済み

割り当てられたメモリ ブロックの数を増やします。

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

*_Nx*\
増分値。

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 このメンバー関数は、to 演算子による呼び出しが成功するたびに呼び出され `cache_freelist::allocate` **`new`** ます。 引数 *_Nx* は、演算子によって割り当てられたチャンク内のメモリブロックの数です **`new`** 。

## <a name="max_fixed_sizedeallocated"></a><a name="deallocated"></a> max_fixed_size::d eallocated

割り当てられたメモリ ブロックの数を減らします。

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

*_Nx*\
増分値。

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 このメンバー関数は、to 演算子による各呼び出しの後に呼び出され `cache_freelist::deallocate` **`delete`** ます。 引数 *_Nx* は、演算子によって割り当て解除されたチャンク内のメモリブロックの数です **`delete`** 。

## <a name="max_fixed_sizefull"></a><a name="full"></a> max_fixed_size:: full

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

**`true`** の場合は `Max <= _Nblocks` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出しでが返された場合 **`true`** 、は `deallocate` メモリブロックをフリーリストに格納します。 false を返す場合は、 `deallocate` 演算子を呼び出して **`delete`** ブロックの割り当てを解除します。

## <a name="max_fixed_sizemax_fixed_size"></a><a name="max_fixed_size"></a> max_fixed_size:: max_fixed_size

`max_fixed_size` 型のオブジェクトを構築します。

```cpp
max_fixed_size();
```

### <a name="remarks"></a>解説

このコンストラクターは、格納された値 `_Nblocks` をゼロに初期化します。

## <a name="max_fixed_sizereleased"></a><a name="released"></a> max_fixed_size:: 解放されました

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

格納された `_Nblocks`を減らします。 `released`現在の[最大クラス](../standard-library/allocators-header.md)のメンバー関数は、 `cache_freelist::allocate` フリーリストからメモリブロックが削除されるたびに、によって呼び出されます。

## <a name="max_fixed_sizesaved"></a><a name="saved"></a> max_fixed_size:: saved

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納された値 `_Nblocks` を増やします。 このメンバー関数は、`cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
