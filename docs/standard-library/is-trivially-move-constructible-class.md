---
title: is_trivially_move_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: a1aef356716fac903b4e44a358602c709572e8ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544353"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible クラス

型に自明な移動コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は自明な移動コンス トラクターを持つ、それ以外の場合は false を保持するクラスです。

クラスの移動コンス トラクター *Ty*は簡単では場合。

暗黙的に宣言されている

そのパラメーターの型が暗黙的な宣言のものと同じである

クラスは、 *Ty*仮想関数がありません

クラスは、 *Ty*仮想基底クラスがありません

クラスに揮発性の非静的データ メンバーがない

すべての直接の基底クラスの*Ty*自明な移動コンス トラクターがあります。

クラス型のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある

クラスの型配列のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
