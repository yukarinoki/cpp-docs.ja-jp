---
title: is_literal_type クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: d5b750755f2499c89e91e497ed03244a11484871
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212255"
---
# <a name="is_literal_type-class"></a>is_literal_type クラス

型を変数として使用できるか、または **`constexpr`** 関数から構築、使用、または返すかをテストし **`constexpr`** ます。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型*T*が*リテラル型*である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 リテラル型は **`void`** 、スカラー型、参照型、リテラル型の配列、またはリテラルクラス型のいずれかです。 リテラルクラス型は、自明なデストラクターを持つクラス型、つまり集計型であるか、少なくとも1つの移動できない非コピーコンストラクターを持つクラス型で、 **`constexpr`** その基本クラスと非静的データメンバーのすべてが非 volatile リテラル型です。 リテラルの型は常にリテラル型ですが、リテラル型の概念には、コンパイラがコンパイル時にとして評価できるすべてのものが含まれ **`constexpr`** ます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
