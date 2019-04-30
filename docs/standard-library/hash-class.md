---
title: hash クラス
ms.date: 11/04/2016
f1_keywords:
- functional/std::hash
- bitset/std::hash
- memory/std::hash
- string/std::hash
- system_error/std::hash
- thread/std::hash
- typeindex/std::hash
- vector/std::hash
- XSTDDEF/std::hash
- xstring/std::hash
helpviewer_keywords:
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
- std::hash [C++]
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
ms.openlocfilehash: 2f7206e3764df384004b78e6df2127833a784f70
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405093"
---
# <a name="hash-class"></a>hash クラス

値のハッシュ コードを計算します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct hash {
    size_t operator()(Ty val) const;
};
```

## <a name="remarks"></a>Remarks

この関数オブジェクトは、*Ty* 型の値をインデックス値の分布にマッピングするのに適したハッシュ関数を定義します。 メンバー `operator()` は、テンプレート クラス `unordered_map`、`unordered_multimap`、`unordered_set`、および `unordered_multiset` での使用に適している *val* のハッシュ コードを返します。 標準ライブラリでは、基本型の特殊化を提供します。*Ty*任意のスカラー型、ポインター型と列挙型を含む場合があります。 また、ライブラリ型 `string`、`wstring`、`u16string`、`u32string`、`string_view`、`wstring_view`、`u16string_view`、`u32string_view`、`bitset`、`error_code`、`error_condition`、`optional`、`shared_ptr`、`thread`、`type_index`、`unique_ptr`、`variant`、および `vector<bool>` の特殊化があります。

## <a name="example"></a>例

```cpp
// std__functional__hash.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>
#include <unordered_set>

int main()
    {
    std::unordered_set<int, std::hash<int> > c0;
    c0.insert(3);
    std::cout << *c0.find(3) << std::endl;

    return (0);
    }
```

```Output
3
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<unordered_map>](../standard-library/unordered-map.md)<br/>
[unordered_multimap クラス](../standard-library/unordered-multimap-class.md)<br/>
[unordered_multiset クラス](../standard-library/unordered-multiset-class.md)<br/>
[<unordered_set>](../standard-library/unordered-set.md)<br/>
