---
title: aligned_storage クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_storage
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
ms.openlocfilehash: 741106888cdab63a75e090e860269f125c35efa6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623828"
---
# <a name="aligned_storage-class"></a>aligned_storage クラス

適切にアライメントされた型を作成します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Len, std::size_t Align>
struct aligned_storage;

template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>
using aligned_storage_t = typename aligned_storage<Len, Align>::type;
```

### <a name="parameters"></a>パラメーター

*Len*\
オブジェクトのサイズ。

*位置*\
オブジェクトのアライメント。

## <a name="remarks"></a>Remarks

テンプレートメンバー typedef `type` は、アラインメントの*Align*と size *Len*を持つ POD 型のシノニムです。 *Align*は `alignment_of<T>::value` 、何らかの型 `T` 、または既定のアラインメントと同じである必要があります。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

typedef std::aligned_storage<sizeof (int),
    std::alignment_of<double>::value>::type New_type;
int main()
    {
    std::cout << "alignment_of<int> == "
        << std::alignment_of<int>::value << std::endl;
    std::cout << "aligned to double == "
        << std::alignment_of<New_type>::value << std::endl;

    return (0);
    }
```

```Output
alignment_of<int> == 4
aligned to double == 8
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](type-traits.md)\
[alignment_of クラス](alignment-of-class.md)
