---
description: '詳細情報: is_nothrow_copy_assignable クラス'
title: is_nothrow_copy_assignable クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
ms.openlocfilehash: 43618158e33a393012a9f7a4a3ad14c816e3cd6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230810"
---
# <a name="is_nothrow_copy_assignable-class"></a>is_nothrow_copy_assignable クラス

スローしないことがコンパイラに判明しているコピー代入演算子が型にあるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型述語のインスタンスは、が true を保持する参照可能 type *T* に対して true を保持 `is_nothrow_assignable<T&, const T&>` します。それ以外の場合は、false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_nothrow_assignable クラス](../standard-library/is-nothrow-assignable-class.md)
