---
description: '詳細情報: allocator_suballoc クラス'
title: allocator_suballoc クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
ms.openlocfilehash: 7e542b4b8f419f1ac219c63b113aced7e0bd7cda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163588"
---
# <a name="allocator_suballoc-class"></a>allocator_suballoc クラス

[Cache_suballoc](cache-suballoc-class.md)型のキャッシュ *を使用して、型の* オブジェクトのストレージ割り当てと解放を管理するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>パラメーター

*各種*\
アロケーターによって割り当てられた要素の型。

## <a name="remarks"></a>解説

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)マクロは、次のステートメントでこのクラスを *name* パラメーターとして渡します。`ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[\<allocators>](allocators-header.md)
