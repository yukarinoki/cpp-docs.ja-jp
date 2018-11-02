---
title: allocator_unbounded クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: 4e5bf54b386a3c3fe4e2604a78437275707acbfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586291"
---
# <a name="allocatorunbounded-class"></a>allocator_unbounded クラス

記憶域の割り当てと型のオブジェクトの解放を管理するオブジェクトを表します*型*型のキャッシュを使用して[cache_freelist](../standard-library/cache-freelist-class.md)によって管理されている長さを[max_unbounded](../standard-library/max-unbounded-class.md).

## <a name="syntax"></a>構文

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Type*|アロケーターによって割り当てられた要素の型。|

## <a name="remarks"></a>Remarks

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)マクロとしてこのクラスを渡す、*名前*次のステートメントのパラメーター。 `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
