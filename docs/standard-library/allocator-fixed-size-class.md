---
title: allocator_fixed_size クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_fixed_size
- allocators/stdext::allocator_fixed_size
- stdext::allocators::allocator_fixed_size
helpviewer_keywords:
- stdext::allocators [C++], allocator_fixed_size
- stdext::allocator_fixed_size
ms.assetid: 138f3ef8-b0b3-49c3-9486-58f2213c172f
ms.openlocfilehash: 340a4e51c82f1799ebea138ce230393825b9e636
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562611"
---
# <a name="allocator_fixed_size-class"></a>allocator_fixed_size クラス

[Max_fixed_size](max-fixed-size-class.md)によって管理される長さの[cache_freelist](cache-freelist-class.md)型のキャッシュ*を使用して、型の*オブジェクトのストレージ割り当てと解放を管理するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Type>
class allocator_fixed_size;
```

### <a name="parameters"></a>パラメーター

*各種*\
アロケーターによって割り当てられた要素の型。

## <a name="remarks"></a>解説

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)マクロは、次のステートメントでこのクラスを*name*パラメーターとして渡します。`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_fixed_size<10>), SYNC_DEFAULT, allocator_fixed_size);`

## <a name="requirements"></a>必要条件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[\<allocators>](allocators-header.md)
