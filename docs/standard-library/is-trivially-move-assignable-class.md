---
title: is_trivially_move_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 324e4a1f1bd3528f09f21c5e485ac814038b7517
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448378"
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable クラス

型が自明なムーブ代入演算子を持つかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>パラメーター

*~* \
照会する型。

## <a name="remarks"></a>Remarks

型*Ty*が自明なムーブ代入演算子を持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

クラス*Ty*の移動代入演算子は、次のような場合に自明です。

暗黙的に指定されている

クラス*Ty*に仮想関数がありません。

クラス*Ty*に仮想基底がありません

クラス型のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある

クラスの型配列のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
