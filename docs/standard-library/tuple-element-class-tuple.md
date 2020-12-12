---
description: '詳細情報: tuple_element クラス'
title: tuple_element クラス
ms.date: 11/04/2016
f1_keywords:
- utility/std::tuple_element
helpviewer_keywords:
- std::tuple_element
ms.assetid: 4c51a6c1-ce81-462f-8c6c-291d69f2b77c
ms.openlocfilehash: dea9f883c2ae8d0a071f894405059ddb5f2090af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168970"
---
# <a name="tuple_element-class"></a>tuple_element クラス

`tuple` 要素をラップします。 `array` 要素および `pair` 要素のラップの特殊化。

## <a name="syntax"></a>構文

```cpp
// CLASS tuple_element (find element by index)
template <size_t Index, class Tuple>
   struct tuple_element;

// tuple_element for const
template <size_t Index, class Tuple>
   struct tuple_element<Index, const Tuple>;

// tuple_element for volatile
template <size_t Index, class Tuple>
   struct tuple_element<Index, volatile Tuple>;

// tuple_element for const volatile
template <size_t Index, class Tuple>
   struct tuple_element<Index, const volatile Tuple>;

// Helper typedef
template <size_t Index, class Tuple>
   using tuple_element_t = typename tuple_element<Index, Tuple>::type;

// Specialization for arrays
template <size_t Index, class Elem, size_t Size>
   struct tuple_element<Index, array<Elem, Size>>;

// Specializations for pairs
// struct to determine type of element 0 in pair
template <class T1, class T2>
   struct tuple_element<0, pair<T1, T2>>;

// struct to determine type of element 1 in pair
template <class T1, class T2>
   struct tuple_element<1, pair<T1, T2>>;
```

### <a name="parameters"></a>パラメーター

*[インデックス]* \
指定した要素のインデックス。

*タプル*\
タプルの型。

*Elem*\
配列要素の型。

*サイズ*\
配列のサイズ。

*T1*\
ペア内の最初の要素の型。

*T2*\
ペアの 2 番目の要素の型。

## <a name="remarks"></a>解説

クラステンプレートには、 `tuple_element` `type` タプル型の *タプル* のインデックス *インデックス* にある型のシノニムである、入れ子になった typedef があります。

Typedef `tuple_element_t` は `tuple_element<Index, Tuple>::type` の便利なエイリアスです。

配列のクラステンプレートの特殊化は、 `array` 要素の組としてのインターフェイスを提供し `Size` ます。各要素は同じ型を持ちます。 それぞれの特殊化には `type` 、の *Index* 要素の型のシノニムである入れ子になった typedef があり `array` ます。 const volatile の制限が保持されます。

`pair` の型のテンプレートの特殊化では、それぞれ 1 つのメンバーの typedef である `type` を提供します。これはペアの指定された位置にある要素の型のシノニムであり、const または volatile の制限が保持されます。 Typedef `tuple_element_t` は `tuple_element<N, pair<T1, T2>>::type` の便利なエイリアスです。

[Get Function &lt; ユーティリティ &gt; ](../standard-library/utility-functions.md#get)を使用して、指定した位置、または指定した型の要素を返します。

## <a name="example-get-an-element-from-a-tuple"></a>例: 組から要素を取得する

```cpp
#include <tuple>
#include <string>
#include <iostream>

using namespace std;
typedef tuple<int, double, string> MyTuple;

int main() {
    MyTuple c0{ 0, 1.5, "Tail" };

    tuple_element_t<0, MyTuple> val = get<0>(c0); //get by index
    tuple_element_t<1, MyTuple> val2 = get<1>(c0);
    tuple_element_t<2, MyTuple> val3 = get<string>(c0); // get by type

    cout << val << " " << val2 << " " << val3 << endl;
}
```

```Output
0 1.5 Tail
```

## <a name="example-get-an-element-from-an-array"></a>例: 配列から要素を取得する

```cpp
#include <array>
#include <iostream>

using namespace std;
typedef array<int, 4> MyArray;

int main()
{
    MyArray c0 { 0, 1, 2, 3 };

    for (const auto& e : c0)
    {
        cout << e << " ";
    }
    cout << endl;

    // display first element "0"
    tuple_element<0, MyArray>::type val = c0.front();
    cout << val << endl;
}
```

```Output
0 1 2 3
0
```

## <a name="example-get-an-element-from-a-pair"></a>例: ペアから要素を取得する

```cpp
#include <utility>
#include <iostream>

using namespace std;

typedef pair<int, double> MyPair;
int main() {
    MyPair c0(0, 1.333);

    // display contents "0 1"
    cout << get<0>(c0) << " ";
    cout << get<1>(c0) << endl;

    // display first element "0 " by index
    tuple_element<0, MyPair>::type val = get<0>(c0);
    cout << val << " ";

    // display second element by type
    tuple_element<1, MyPair>::type val2 = get<double>(c0);
    cout << val2 << endl;
}
```

```Output
0 1.333
0 1.333
```

## <a name="requirements"></a>要件

**ヘッダー:**\<tuple>

**ヘッダー:** \<array> (配列の特殊化用)

**ヘッダー:** \<utility> (ペアの特殊化の場合)

**名前空間:** std
