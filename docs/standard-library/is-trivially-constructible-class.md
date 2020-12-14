---
description: '詳細情報: is_trivially_constructible クラス'
title: is_trivially_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 4a5c3e20366c4e87aa731c6d6a69787286b947b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247632"
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
*T* のコンストラクターで一致する引数の型。

## <a name="remarks"></a>解説

型の述語のインスタンスは、引数の型を使用して型 *T* が普通に構築可能な場合は true を保持します。それ *以外の場合* は、false を保持します。 変数定義 `T t(std::declval<Args>()...);` が整形式であり、重要でない操作を呼び出さないことがわかっている場合、型 T は普通に構築可能です。 *T* と *Args* 内のすべての型は、完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
