---
title: allocator_unbounded クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
dev_langs:
- C++
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0108b8d02c275cb4e498cd3e9df00b87b7cae28f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="allocatorunbounded-class"></a>allocator_unbounded クラス

[cache_freelist](../standard-library/cache-freelist-class.md) 型のキャッシュと [max_unbounded](../standard-library/max-unbounded-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Type`|アロケーターによって割り当てられた要素の型。|

## <a name="remarks"></a>コメント

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) マクロは、このクラスを次のステートメント内の `name` パラメーターとして渡します: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>要件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
