---
title: Swap 関数 (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Swap
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
ms.openlocfilehash: 97d24f1f4453e948c621651e029254db1b0de712
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027561"
---
# <a name="swap-function-wrl"></a>Swap 関数 (WRL)

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW inline void Swap(
   _Inout_ T& left,
   _Inout_ T& right
);
```

### <a name="parameters"></a>パラメーター

*左へ*<br/>
最初の引数。

*右*<br/>
2 番目の引数。

## <a name="return-value"></a>戻り値

## <a name="remarks"></a>Remarks

指定された 2 つの引数の値を交換します。

## <a name="requirements"></a>必要条件

**ヘッダー:** internal.h

**名前空間:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)