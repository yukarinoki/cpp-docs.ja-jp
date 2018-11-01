---
title: conditional クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: be81a1bc32f2f86f1d79970868933bddb8dc3620
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523020"
---
# <a name="conditional-class"></a>conditional クラス

指定された条件に基づいて、2 つの型のいずれかを選択します。

## <a name="syntax"></a>構文

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>パラメーター

*B*<br/>
選択される型を決定する値。

*T1*<br/>
B が true の場合の型の結果。

*T2*<br/>
B が false の場合の型の結果。

## <a name="remarks"></a>Remarks

テンプレート メンバー typedef`conditional<B, T1, T2>::type`に評価される*T1*とき*B*に評価される**true**に評価されると*T2*とき*B*に評価される**false**します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
