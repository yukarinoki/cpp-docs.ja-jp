---
title: CompareStringOrdinal メソッド
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: 61ca0cb6d8afc07b73e33a2e5bc3dc10daacc210
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593376"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
比較する最初の HSTRING です。

*rhs*<br/>
比較する 2 つ目の HSTRING です。

## <a name="return-value"></a>戻り値

|[値]|条件|
|-----------|---------------|
|-1|*lhs*がより小さい*rhs*します。|
|0|*lhs* equals *rhs*します。|
|1|*lhs*がより大きい*rhs*します。|

## <a name="remarks"></a>Remarks

2 つの指定した HSTRING オブジェクトを比較し、並べ替え順序でそれらの相対位置を示す整数を返します。

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)