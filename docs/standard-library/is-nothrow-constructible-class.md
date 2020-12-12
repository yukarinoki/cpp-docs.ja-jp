---
description: '詳細情報: is_nothrow_constructible クラス'
title: is_nothrow_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 0bb822a42d149a552f18ff4d1b1c723ef9b88172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323582"
---
# <a name="is_nothrow_constructible-class"></a>is_nothrow_constructible クラス

指定された引数型の使用時に型を構築できるかどうか、およびスローしないと判明しているかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

*Value*\
*T* のコンストラクターで一致する引数の型。

## <a name="remarks"></a>解説

型の述語のインスタンスは、型 *T* が引数の型を引数として使用して構築可能であり、コンストラクターがコンパイラによってスローされない場合に *true を保持* します。それ以外の場合は、false を保持します。 型 *T* は、変数定義が整形式である場合に構築可能です `T t(std::declval<Args>()...);` 。 *T* と *Args* 内のすべての型は、完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
