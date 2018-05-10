---
title: is_nothrow_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 112da495673517f86a00437672ccc52429fbd251
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible クラス

指定された引数型の使用時に型を構築できるかどうか、およびスローしないと判明しているかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

`Args` 引数の型のコンス トラクターで一致するように`T`です。

## <a name="remarks"></a>コメント

型の述語のインスタンスは、型 `T` が `Args` の引数型を使用して構築可能であり、コンストラクターがスローしないとコンパイラによって認識されている場合 true を保持します。それ以外の場合は false を保持します。 型 `T` を構築できるのは、変数定義 `T t(std::declval<Args>()...);` が整形式である場合です。 `T` と `Args` のすべての型は両方とも、完全な型、`void`、または不明なバインドの配列にする必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
