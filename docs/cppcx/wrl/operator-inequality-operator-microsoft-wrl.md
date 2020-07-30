---
title: operator!= 演算子 (Microsoft::WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator!=
ms.assetid: 785435da-87a6-4454-9bce-9d288a96dc26
ms.openlocfilehash: af7088348cd3f52b38f0277fb7d0a973a1ca0e4b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226894"
---
# <a name="operator-operator-microsoftwrl"></a>operator!= 演算子 (Microsoft::WRL)

[Comptr](comptr-class.md)および[comptrref](comptrref-class.md)オブジェクトの非等値演算子。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);
WRL_NOTHROW bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);
WRL_NOTHROW bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
WRL_NOTHROW bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);
WRL_NOTHROW bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);
WRL_NOTHROW bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);
WRL_NOTHROW bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);
WRL_NOTHROW bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>パラメーター

*ある*<br/>
左側のオブジェクト。

*b*<br/>
右側のオブジェクト。

## <a name="return-value"></a>戻り値

**`true`** オブジェクトが等しくない場合は。それ以外の場合は **`false`** 。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
