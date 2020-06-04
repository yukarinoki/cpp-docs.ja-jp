---
title: '&lt;array&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
ms.openlocfilehash: 531ad2936322f90a38631a9450e0ad8a210fdd87
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364907"
---
# <a name="ltarraygt-operators"></a>&lt;array&gt; 演算子

配列\<>ヘッダーには、これらの**配列**非メンバー比較テンプレート関数が含まれます。

||||
|-|-|-|
|[演算子!=](#op_neq)|[演算子&gt;](#op_gt)|[演算子&gt;=](#op_gt_eq)|
|[演算子&lt;](#op_lt)|[演算子&lt;=](#op_lt_eq)|[演算子==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>演算子!=

配列の比較 (等しくない)。

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*\
要素の型。

*N*\
配列のサイズ。

*左*\
比較する左のコンテナー。

*そうです*\
比較する右のコンテナー。

### <a name="remarks"></a>解説

このテンプレート関数は `!(left == right)` を返します。

### <a name="example"></a>例

```cpp
// std__array__operator_ne.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 != c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 != c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorlt"></a><a name="op_lt"></a>演算子&lt;

配列の比較 (より小さい)。

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*\
要素の型。

*N*\
配列のサイズ。

*左*\
比較する左のコンテナー。

*そうです*\
比較する右のコンテナー。

### <a name="remarks"></a>解説

テンプレート関数は、クラス`operator<`テンプレート[配列 Class](../standard-library/array-class-stl.md)の 2 つのオブジェクトを比較するためにオーバーロードします。 `lexicographical_compare(left.begin(), left.end(), right.begin())` が返されます。

### <a name="example"></a>例

```cpp
// std__array__operator_lt.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 < c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 < c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>演算子&lt;=

配列の比較 (以下)。

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*\
要素の型。

*N*\
配列のサイズ。

*左*\
比較する左のコンテナー。

*そうです*\
比較する右のコンテナー。

### <a name="remarks"></a>解説

このテンプレート関数は `!(right < left)` を返します。

### <a name="example"></a>例

```cpp
// std__array__operator_le.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 <= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 <= c0);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="operator"></a><a name="op_eq_eq"></a>演算子==

配列の比較 (等しい)。

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*\
要素の型。

*N*\
配列のサイズ。

*左*\
比較する左のコンテナー。

*そうです*\
比較する右のコンテナー。

### <a name="remarks"></a>解説

テンプレート関数は、クラス`operator==`テンプレート[配列 Class](../standard-library/array-class-stl.md)の 2 つのオブジェクトを比較するためにオーバーロードします。 `equal(left.begin(), left.end(), right.begin())` が返されます。

### <a name="example"></a>例

```cpp
// std__array__operator_eq.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 == c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 == c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="operatorgt"></a><a name="op_gt"></a>演算子&gt;

配列の比較 (より大きい)。

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*\
要素の型。

*N*\
配列のサイズ。

*左*\
比較する左のコンテナー。

*そうです*\
比較する右のコンテナー。

### <a name="remarks"></a>解説

このテンプレート関数は `(right < left)` を返します。

### <a name="example"></a>例

```cpp
// std__array__operator_gt.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 > c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 > c0);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>演算子&gt;=

配列の比較 (以上)。

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*\
要素の型。

*N*\
配列のサイズ。

*左*\
比較する左のコンテナー。

*そうです*\
比較する右のコンテナー。

### <a name="remarks"></a>解説

このテンプレート関数は `!(left < right)` を返します。

### <a name="example"></a>例

```cpp
// std__array__operator_ge.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 >= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 >= c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="see-also"></a>関連項目

[\<配列>](../standard-library/array.md)
