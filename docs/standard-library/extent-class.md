---
title: extent クラス | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e6df4526eea3b0b8b4e91fa4f3e6a89cdd8adb7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964311"
---
# <a name="extent-class"></a>extent クラス

配列の次元を取得します。

## <a name="syntax"></a>構文

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>パラメーター

*Ty*照会する型。

*I*配列がクエリにバインドします。

## <a name="remarks"></a>Remarks

場合*Ty*が配列型を持つ少なくとも*は*によって指定されたディメンションのディメンション型クエリを保持要素の数*は*します。場合*Ty*が配列型でないか、そのランクがより小さい*は*、場合*は*ゼロと*Ty*の種類は"の不明の配列にバインドされている`U`"、型のクエリが 0 の値を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }

```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_all_extents クラス](../standard-library/remove-all-extents-class.md)<br/>
[remove_extent クラス](../standard-library/remove-extent-class.md)<br/>
