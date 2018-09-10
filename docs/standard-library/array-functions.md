---
title: '&lt;array&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- array/std::array::get
- array/std::get
- array/std::swap
dev_langs:
- C++
ms.assetid: e0700a33-a833-4655-8735-16e71175efc8
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::array [C++], get
- std::get [C++]
- std::swap [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: a67a22b8236646b549032e236006cd4855c3a43c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108727"
---
# <a name="ltarraygt-functions"></a>&lt;array&gt; 関数

\<Array > ヘッダーには、2 つの非メンバー関数が含まれています。`get`と`swap`、で動作する**配列**オブジェクト。

|||
|-|-|
|[get](#get)|[swap](#swap)|

## <a name="get"></a>  get

配列の指定した要素への参照を返します。

```cpp
template <int Index, class T, size_t N>
constexpr T& get(array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr const T& get(const array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr T&& get(array<T, N>&& arr) noexcept;
```

### <a name="parameters"></a>パラメーター

*Index*<br/>
要素のオフセット。

*T*<br/>
要素の型。

*N*<br/>
配列の要素数。

*arr*<br/>
選択する配列。

### <a name="example"></a>例

```cpp
#include <array>
#include <iostream>

using namespace std;

typedef array<int, 4> MyArray;

int main()
{
    MyArray c0 { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& e : c0)
    {
        cout << " " << e;
    }
    cout << endl;

    // display odd elements " 1 3"
    cout << " " << get<1>(c0);
    cout << " " << get<3>(c0) << endl;
}
```

```Output
0 1 2 3
1 3
```

## <a name="swap"></a>  swap

非メンバー テンプレートの特殊化`std::swap`交換する 2 つ**配列**オブジェクト。

```cpp
template <class Ty, std::size_t N>
void swap(array<Ty, N>& left, array<Ty, N>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
要素の型。

*N*<br/>
配列のサイズ。

*left*<br/>
交換する最初の配列。

*right*<br/>
交換する 2 番目の配列。

### <a name="remarks"></a>Remarks

このテンプレート関数は、`left.swap(right)` を実行します。

### <a name="example"></a>例

```cpp
// std__array__swap.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
0 1 2 3
```

## <a name="see-also"></a>関連項目

[\<array>](../standard-library/array.md)<br/>
