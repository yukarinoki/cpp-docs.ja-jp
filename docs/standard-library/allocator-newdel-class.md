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
ms.openlocfilehash: aa5012f6657b2676756d1d8023274a524b451df3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617460"
---
# <a name="allocator_newdel-class"></a>allocator_newdel クラス

**Operator delete**を使用してメモリブロックの割り当てを解除し、メモリブロックを割り当てる**新しい演算子**を使用するアロケーターを実装します。

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

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)マクロは、次のステートメントでこのクラスを*name*パラメーターとして渡します。`ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>必要条件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[\<allocators>](allocators-header.md)
