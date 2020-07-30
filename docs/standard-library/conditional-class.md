---
title: conditional クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: 03ec6248ba3361622ad061ac3854a60995148f4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228376"
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

*B*\
選択される型を決定する値。

*T1*\
B が true の場合の型の結果。

*T2*\
B が false の場合の型の結果。

## <a name="remarks"></a>解説

B がと評価されると、テンプレートメンバー typedef は `conditional<B, T1, T2>::type` *T1*に評価され、 *B* **`true`** *b*がに評価されると*T2*に評価され **`false`** ます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
