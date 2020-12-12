---
description: '詳細情報: is_default_constructible クラス'
title: is_default_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_default_constructible
helpviewer_keywords:
- is_default_constructible
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
ms.openlocfilehash: 9c5365ee6e2e2b7382b5dd5f17cce2afd0ce8932
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323783"
---
# <a name="is_default_constructible-class"></a>is_default_constructible クラス

型が既定のコンストラクターを持つかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型 *T* が既定のコンストラクターを持つクラス型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 これは、述語 `is_constructible<T>`と同じです。 型 *T* は完全な型、 **`void`** 、または不明なバインドの配列である必要があります。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}
```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
