---
description: '詳細: ディケイ Class'
title: decay クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 6f6a1ebd31af44a48eaf400f9dccefdbd8ca3d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324602"
---
# <a name="decay-class"></a>decay クラス

値で渡された型を生成します。 型を非参照、非定数、非揮発性にします。または、関数からの型または配列型へのポインターを作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

型が引数として値で渡されたかのように結果の型を生成するには、decay テンプレートを使います。 クラステンプレートメンバー typedef は、 `type` 次の段階で定義されている変更された型を保持します。

- 型 `U` が `remove_reference<T>::type` として定義されます。

- `is_array<U>::value` が true の場合、修飾型 `type` は `remove_extent<U>::type *` になります。

- `is_function<U>::value` が true の場合、修飾型 `type` は `add_pointer<U>::type` になります。

- それ以外の場合、修飾型 `type` は `remove_cv<U>::type` になります。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
