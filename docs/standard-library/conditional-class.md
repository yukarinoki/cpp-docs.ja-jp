---
title: conditional クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d51397080267dd50f012b274e95ac4c9aa4fa64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
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

`B` 選択した種類を決定する値。

`T1` B が true の場合の型の結果。

`T2` B が false の場合の型の結果。

## <a name="remarks"></a>コメント

テンプレート メンバー typedef `conditional<B, T1, T2>::type` は、 `T1` が `B` に評価されるときは `true`として、 `T2` が `B` に評価されるときは `false`として評価されます。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
