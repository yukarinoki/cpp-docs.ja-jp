---
title: max_none クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
ms.openlocfilehash: c49ceec72be62d8ff3125f04d97bbb6952501677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370973"
---
# <a name="max_none-class"></a>max_none クラス

[freelist](../standard-library/freelist-class.md) オブジェクトを最長値ゼロまでに制限する[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*最大*|`freelist` に格納する要素の最大数を決定する、最大クラス。|

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

## <a name="max_noneallocated"></a><a name="allocated"></a>max_none::割り当て済み

割り当てられたメモリ ブロックの数を増やします。

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Nx*|増分値。|

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 これは、オペレータ`cache_freelist::allocate`**new**への呼び出しが成功するたびに呼び出されます。 引数 *_Nx*は、演算子**new**によって割り当てられたチャンク内のメモリ ブロックの数です。

## <a name="max_nonedeallocated"></a><a name="deallocated"></a>max_none::d割り当て済み

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

## <a name="max_nonefull"></a><a name="full"></a>max_none::フル

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

このメンバ関数は常に**true**を返します。

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出し**true**が`deallocate`true を返す場合は、メモリ ブロックを空きリストに配置します。**false**を返す`deallocate`場合は、演算子**delete**を呼び出してブロックの割り当てを解除します。

## <a name="max_nonereleased"></a><a name="released"></a>max_none::リリース済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。

## <a name="max_nonesaved"></a><a name="saved"></a>max_none::保存済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 `cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
