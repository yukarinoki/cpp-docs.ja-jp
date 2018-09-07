---
title: aligned_storage Class | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::aligned_storage
dev_langs:
- C++
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aabd4a68e4ec9d9da96eff14dcf69c5bd667cc06
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107506"
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

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[alignment_of クラス](../standard-library/alignment-of-class.md)<br/>
