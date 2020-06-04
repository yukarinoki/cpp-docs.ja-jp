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
ms.openlocfilehash: fbc4351297ab8a3cc90a2a77fa31c3b134f10eab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370993"
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
|[完全](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|
|[リリース](#released)|フリー リスト上のメモリ ブロックの数を減らします。|
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="max_unboundedallocated"></a><a name="allocated"></a>max_unbounded::割り当て済み

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

## <a name="max_unboundeddeallocated"></a><a name="deallocated"></a>max_unbounded::d割り当て済み

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

## <a name="max_unboundedfull"></a><a name="full"></a>max_unbounded::フル

フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。

```cpp
bool full();
```

### <a name="return-value"></a>戻り値

メンバー関数は常に**false**を返します。

### <a name="remarks"></a>解説

このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出し**true**が`deallocate`true を返す場合は、メモリ ブロックを空きリストに配置します。false を返す`deallocate`場合は、演算子**delete**を呼び出してブロックの割り当てを解除します。

## <a name="max_unboundedreleased"></a><a name="released"></a>max_unbounded::リリース済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void released();
```

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。

## <a name="max_unboundedsaved"></a><a name="saved"></a>max_unbounded::保存済み

フリー リスト上のメモリ ブロックの数を減らします。

```cpp
void saved();
```

### <a name="remarks"></a>解説

このメンバー関数は何も処理を行いません。 `cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
