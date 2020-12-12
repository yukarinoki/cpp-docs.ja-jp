---
description: '詳細情報: is_nothrow_move_constructible クラス'
title: is_nothrow_move_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
ms.openlocfilehash: 9ab9d1dfdba532bfda3111831f389a94a49af936
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323595"
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

型に nothrow 移動 *コンストラクターがある* 場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
