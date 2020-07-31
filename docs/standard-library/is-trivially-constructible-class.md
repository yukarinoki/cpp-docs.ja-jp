---
title: is_trivially_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 1f835dd348c6ef7f2ca7cd01f04c5afc059a55b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222330"
---
# <a name="is_trivially_constructible-class"></a>is_trivially_constructible クラス

指定した引数型の使用時に型を自明に構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

*Value*\
*T*のコンストラクターで一致する引数の型。

## <a name="remarks"></a>解説

型の述語のインスタンスは、引数の型を使用して型*T*が普通に構築可能な場合は true を保持します。それ*以外の場合*は、false を保持します。 変数*T*定義 `T t(std::declval<Args>()...);` が整形式であり、重要でない操作を呼び出さないことがわかっている場合、型 T は普通に構築可能です。 *T*と*Args*内のすべての型は、完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
