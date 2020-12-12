---
description: '詳細情報: is_move_constructible クラス'
title: is_move_constructible クラス
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 05ef640b2841eb3ab66f6d5a6d3b8ede7acf2754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323634"
---
# <a name="is_move_constructible-class"></a>is_move_constructible クラス

移動操作を使用して型を構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
評価される型。

## <a name="remarks"></a>解説

**`true`** 移動操作を使用して型 *T* を構築できる場合にに評価される型述語。 この述語は `is_constructible<T, T&&>` と同じです。 移動コンストラクターを持たないが、引数を受け入れるコピーコンストラクターを持つ型 *T* は `const T&` 、を満たし `std::is_move_constructible` ます。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
