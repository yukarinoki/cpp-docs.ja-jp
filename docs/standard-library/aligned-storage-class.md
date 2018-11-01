---
title: aligned_storage クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_storage
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
ms.openlocfilehash: 0da2b206cd40f84ac33860c84bbb6a86f6f47fc0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477286"
---
# <a name="alignedstorage-class"></a>aligned_storage クラス

適切にアライメントされた型を作成します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Len, std::size_t Align>
struct aligned_storage;

template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>
using aligned_storage_t = typename aligned_storage<Len, Align>::type;
```

### <a name="parameters"></a>パラメーター

*len*<br/>
オブジェクトのサイズ。

*配置*<br/>
オブジェクトのアライメント。

## <a name="remarks"></a>Remarks

テンプレート メンバー typedef `type` POD 型の配置のシノニムです*Align*とサイズ*Len*します。 *Align*に等しくなければ`alignment_of<T>::value`何らかの種類の`T`、または既定の配置。

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

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[alignment_of クラス](../standard-library/alignment-of-class.md)<br/>
