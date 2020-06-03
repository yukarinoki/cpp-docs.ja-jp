---
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
ms.openlocfilehash: 7f75dd71caa3cfcfec19264b1da62c6d47a3e01d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371005"
---
# <a name="max_fixed_size-class"></a>max_fixed_size クラス

[freelist](../standard-library/freelist-class.md) オブジェクトを固定の最長値までに制限する[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*最大*|`freelist` に格納する要素の最大数を決定する、最大クラス。|

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[max_fixed_size](#max_fixed_size)|`max_fixed_size` 型のオブジェクトを構築します。|

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

## <a name="max_fixed_sizeallocated"></a><a name="allocated"></a>max_fixed_size:割り当て済み

割り当てられたメモリ ブロックの数を増やします。

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 このメンバー関数は、オペレーター **new**を`cache_freelist::allocate`呼び出した後に呼び出されます。 引数 *_Nx*は、演算子**new**によって割り当てられたチャンク内のメモリ ブロックの数です。

## <a name="max_fixed_sizedeallocated"></a><a name="deallocated"></a>max_fixed_size::d割り当て済み

割り当てられたメモリ ブロックの数を減らします。

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 このメンバー関数は、オペレーター delete`cache_freelist::deallocate`を呼び出すたびに呼び出**されます**。 引数 *_Nx*は、演算子 delete によって割り当て解除されたチャンク内のメモリ ブロックの数**です**。

## <a name="max_fixed_sizefull"></a><a name="full"></a>max_fixed_size::フル

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

**true** `Max <= _Nblocks`の場合は、それ以外の場合**は false。**

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出し**true**が`deallocate`true を返す場合は、メモリ ブロックを空きリストに配置します。false を返す`deallocate`場合は、演算子**delete**を呼び出してブロックの割り当てを解除します。

## <a name="max_fixed_sizemax_fixed_size"></a><a name="max_fixed_size"></a>max_fixed_size::max_fixed_size

`max_fixed_size` 型のオブジェクトを構築します。

```cpp
max_fixed_size();
```

### <a name="remarks"></a>解説

このコンストラクターは、格納された値 `_Nblocks` をゼロに初期化します。

## <a name="max_fixed_sizereleased"></a><a name="released"></a>max_fixed_size::リリース済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

格納された `_Nblocks`を減らします。 現在`released`の[max クラス](../standard-library/allocators-header.md)のメンバー関数は、`cache_freelist::allocate`空きリストからメモリ ブロックを削除するたびに呼び出されます。

## <a name="max_fixed_sizesaved"></a><a name="saved"></a>max_fixed_size::保存済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納された値 `_Nblocks` を増やします。 このメンバー関数は、`cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
