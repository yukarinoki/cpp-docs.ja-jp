---
title: is_trivially_move_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad5631fc5d689ccb6632ac230aebdaf40f18f80
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106484"
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

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
