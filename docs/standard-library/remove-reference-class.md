---
title: remove_reference クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_reference
dev_langs:
- C++
helpviewer_keywords:
- remove_reference class
- remove_reference
ms.assetid: 294e1965-3ae3-46ee-bc42-4fdf60c24717
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5aaf151d7591776857c5f731841847e31c41239
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858540"
---
# <a name="removereference-class"></a>remove_reference クラス

型から非参照型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct remove_reference;

template <class T>
using remove_reference_t = typename remove_reference<T>::type;
```

### <a name="parameters"></a>パラメーター

`T` 変更する型。

## <a name="remarks"></a>コメント

`remove_reference<T>` のインスタンスは、`T1` の形式が `T` である場合は、修飾型 `T1&` を保持します。それ以外の場合は、`T` を保持します。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_reference_t<int&> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_reference_t<int&> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_reference_t<int&> == int
```

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_lvalue_reference クラス](../standard-library/add-lvalue-reference-class.md)<br/>
