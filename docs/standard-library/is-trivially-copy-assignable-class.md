---
title: is_trivially_copy_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 831e7c5afdd39980876a8e8284a68fec2084a4e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630985"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable クラス

型が自明なコピー代入演算子を持つかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*は自明なコピー代入演算子を持つ、それ以外の場合は false を保持するクラスです。

クラスの代入コンス トラクター *T*は暗黙的に入力すると、クラスに自明*T*仮想関数、クラスを持たない*T*のクラスの仮想基底がないです。クラス型のすべての非静的データ メンバーが自明な代入演算子、ありのクラスの型配列のすべての非静的データ メンバーのクラスが自明な代入演算子があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
