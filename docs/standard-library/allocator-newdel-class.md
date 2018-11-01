---
title: allocator_newdel クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: eac2fb993eb3e9aab5d043debe6402576d7b49b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440756"
---
# <a name="allocatornewdel-class"></a>allocator_newdel クラス

使用するアロケーターを実装する**delete 演算子**、メモリの割り当てを解除するブロックと**演算子 new**メモリ ブロックを割り当てます。

## <a name="syntax"></a>構文

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Type*|アロケーターによって割り当てられた要素の型。|

## <a name="remarks"></a>Remarks

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)マクロとしてこのクラスを渡す、*名前*次のステートメントのパラメーター。 `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
