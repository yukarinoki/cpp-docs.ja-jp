---
title: is_nothrow_move_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 115a1b6c2157a139786c0b8762a9a614bbcd6deb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217728"
---
# <a name="is_nothrow_move_constructible-class"></a>is_nothrow_move_constructible クラス

型に移動コンストラクターがあるかどうかをテスト **`nothrow`** します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_nothrow_move_constructible;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型に nothrow 移動*コンストラクターがある*場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
