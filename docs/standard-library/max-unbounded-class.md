---
title: max_unbounded クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
ms.openlocfilehash: 8ec0f1c6c84399ef4b3d048a99d1c191541b7c6d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222278"
---
# <a name="max_unbounded-class"></a>max_unbounded クラス

[freelist](../standard-library/freelist-class.md) オブジェクトの最長値を制限しない[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
class max_unbounded
```

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

## <a name="max_unboundedallocated"></a><a name="allocated"></a>max_unbounded:: 割り当て済み

割り当てられたメモリ ブロックの数を増やします。

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 これは、to 演算子による呼び出しが成功するたびに呼び出され `cache_freelist::allocate` **`new`** ます。 引数 *_Nx*は、演算子によって割り当てられたチャンク内のメモリブロックの数です **`new`** 。

## <a name="max_unboundeddeallocated"></a><a name="deallocated"></a>max_unbounded::d eallocated

割り当てられたメモリ ブロックの数を減らします。

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 このメンバー関数は、to 演算子による各呼び出しの後に呼び出され `cache_freelist::deallocate` **`delete`** ます。 引数 *_Nx*は、演算子によって割り当て解除されたチャンク内のメモリブロックの数です **`delete`** 。

## <a name="max_unboundedfull"></a><a name="full"></a>max_unbounded:: full

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

このメンバー関数は常にを返し **`false`** ます。

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出しでが返された場合 **`true`** 、は `deallocate` メモリブロックをフリーリストに格納します。 false を返す場合は、 `deallocate` 演算子を呼び出して **`delete`** ブロックの割り当てを解除します。

## <a name="max_unboundedreleased"></a><a name="released"></a>max_unbounded:: 解放されました

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。

## <a name="max_unboundedsaved"></a><a name="saved"></a>max_unbounded:: saved

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 `cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
