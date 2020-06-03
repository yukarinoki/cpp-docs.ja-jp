---
title: hash クラス
ms.date: 11/04/2016
f1_keywords:
- functional/std::hash
- bitset/std::hash
- memory/std::hash
- string/std::hash
- system_error/std::hash
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
ms.openlocfilehash: aa51e56197ba79afbe2bd2597596c52b23a4f65b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446585"
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

## <a name="remarks"></a>コメント

この関数オブジェクトは、*Ty* 型の値をインデックス値の分布にマッピングするのに適したハッシュ関数を定義します。 メンバー `operator()` は、クラステンプレート `unordered_map`、`unordered_multimap`、`unordered_set`、および `unordered_multiset`で使用するのに適した、 *val*のハッシュコードを返します。 標準ライブラリには、基本型の特殊化が用意されています。*Ty* は、ポインター型や列挙型など、任意のスカラー型にすることができます。 また、ライブラリ型 `string`、`wstring`、`u16string`、`u32string`、`string_view`、`wstring_view`、`u16string_view`、`u32string_view`、`bitset`、`error_code`、`error_condition`、`optional`、`shared_ptr`、`thread`、`type_index`、`unique_ptr`、`variant`、および `vector<bool>` の特殊化があります。

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

## <a name="requirements"></a>要件

**ヘッダー:** \<機能 >

**名前空間:** std

## <a name="see-also"></a>参照

[<unordered_map>](../standard-library/unordered-map.md)\
[unordered_multimap クラス](../standard-library/unordered-multimap-class.md)\
[unordered_multiset クラス](../standard-library/unordered-multiset-class.md)\
[<unordered_set>](../standard-library/unordered-set.md)
