---
title: span クラス (C++ 標準ライブラリ) |Microsoft Docs
ms.date: 05/28/2020
f1_keywords:
- span/std::span
- span/std::span::const_pointer
- span/std::span::const_reference
- span/std::span::difference_type
- span/std::span::element_type
- span/std::span::iterator
- span/std::span::pointer
- span/std::span::reference
- span/std::span::reverse_iterator
- span/std::span::size_type
- span/std::span::value_type
- span/std::span::at
- span/std::span::assign
- span/std::span::back
- span/std::span::begin
- span/std::span::data
- span/std::span::empty
- span/std::span::end
- span/std::span::front
- span/std::span::rbegin
- span/std::span::rend
- span/std::span::size
- span/std::span::size_bytes
- span/std::span::operator=
- span/std::span::operator[]
helpviewer_keywords:
- std::span [C++]
- std::span [C++], const_pointer
- std::span [C++], const_reference
- std::span [C++], difference_type
- std::span [C++], element_type
- std::span [C++], iterator
- std::span [C++], pointer
- std::span [C++], reference
- std::span [C++], reverse_iterator
- std::span [C++], size_type
- std::span [C++], value_type
- std::span [C++], assign
- std::span [C++], at
- std::span [C++], back
- std::span [C++], begin
- std::span [C++], data
- std::span [C++], empty
- std::span [C++], end
- std::span [C++], front
- std::span [C++], rbegin
- std::span [C++], rend
- std::span [C++], size
- std::span [C++], size_bytes
ms.openlocfilehash: e77f57bc56a75406745349e19d03bc26edc5470d
ms.sourcegitcommit: 83ea5df40917885e261089b103d5de3660314104
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85813510"
---
# <a name="span-class-c-standard-library"></a>span クラス (C++ 標準ライブラリ)

連続した一連のオブジェクトの簡易ビューを提供します。 スパンは、組み込みの配列、、またはに格納されているオブジェクトなど、メモリに戻されたオブジェクトの反復処理とインデックス化を安全に行う方法を提供し `std::array` `std::vector` ます。

通常、ポインターとインデックスを使用してバックツーバックオブジェクトのシーケンスにアクセスすると、より `span` 安全で軽量な代替手段となります。

のサイズは、 `span` コンパイル時にテンプレート引数として指定するか、を指定することによって実行時に設定でき `dynamic_extent` ます。

## <a name="syntax"></a>構文

```cpp
template<class T, size_t Extent = dynamic_extent>
class span;
```

### <a name="template-parameters"></a>Template parameters

|パラメーター|説明|
|-|-|
|`T`| スパン内の要素の型。 |
|`Extent`| コンパイル時に指定した場合にスパン内の要素の数。 それ以外の `std::dynamic_extent` 場合は、実行時に要素の数が指定されます。 |

[控除ガイド](#deduction_guides)

## <a name="members"></a>メンバー

| **型定義** | **説明** |
|-|-|
| [const_pointer](#pointer) | 要素へのポインターの型 `const` 。 |
| [const_reference](#reference) | 要素への参照の型 `const` 。 |
| [difference_type](#difference_type) | 2 つの要素間の距離を表す、符号付きの型です。 |
| [element_type](#element_type) | Span 要素の型。 |
| [反](#iterator) | スパンの反復子の型。 |
| [pointer](#pointer) | 要素へのポインターの型です。 |
| [reference](#reference) | 要素への参照の型です。 |
| [reverse_iterator](#reverse_iterator) | スパンの反転反復子の型。 |
| [size_type](#size_type) | スパン内の2つの要素間の符号なし距離の結果の型。 |
| [value_type](#value_type) | 要素の型 ( `const` またはの修飾なし) `volatile` 。 |
| **コンストラクター** | **説明** |
|[スパン](#span)| を構築 `span` します。|
| **反復子のサポート** | **説明** |
|[初め](#begin) | スパン内の最初の要素を指す反復子を取得します。|
|[終わり](#end) | スパンの末尾を指す反復子を取得します。 |
|[rbegin](#rbegin) | スパンの最後の要素を指す反転反復子を取得します。これは、反転スパンの開始部分です。|
|[rend](#rend) | スパンの前を指す反転反復子を取得します。つまり、反転されたスパンの最後です。|
| **アクセス要素**| **説明** |
|[戻る](#back) | スパン内の最後の要素を取得します。|
|[データ](#data) | スパン内の最初の要素のアドレスを取得します。|
|[外側](#front) | スパン内の最初の要素を取得します。|
|[operator\[\]](#op_at) | 指定した位置にある要素にアクセスします。|
| **オブザーバー** | **説明** |
|[empty](#empty)| スパンが空であるかどうかをテストします。|
|[size](#size) | スパン内の要素の数を取得します。|
|[size_bytes](#size_bytes) | スパンのサイズをバイト単位で取得します。|
| **サブ** | **説明**|
| [first](#first_view) | スパンの前からサブスパンを取得します。|
| [last](#last_view) | スパンの背面からサブスパンを取得します。|
| [サブスパン](#sub_view) | スパン内の任意の場所からサブスパンを取得します。|
| **オペレーター** | **説明** |
|[span:: operator =](#op_eq)| スパンを置き換えます。|
|[span:: 演算子\[\]](#op_at)| 指定した位置にある要素を取得します。 |

## <a name="remarks"></a>Remarks

すべて `span` のメンバー関数には、一定時間の複雑さがあります。

またはとは異なり `array` `vector` 、スパンは、その中の要素を "所有" しません。 スパンは、それらのオブジェクトのストレージを所有していないため、その中のアイテムのストレージを解放しません。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<span>

**名前空間:** std

**コンパイラオプション:** /std: c + + latest

## <a name="spanback"></a><a name="back"></a> `span::back`

スパン内の最後の要素を取得します。

```cpp
constexpr reference back() const noexcept;
```

### <a name="return-value"></a>戻り値

スパン内の最後の要素への参照。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    cout << mySpan.back();
}
```

```Output
2
```

## <a name="spanbegin"></a><a name="begin"></a> `span::begin`

スパン内の最初の要素を指す反復子を取得します。

```cpp
constexpr iterator begin() const noexcept;
```

### <a name="return-value"></a>戻り値

スパン内の最初の要素を指す反復子。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto i = mySpan.begin();
    cout << *i;
}
```

```Output
0
```

## <a name="spandata"></a><a name="data"></a> `span::data`

スパンデータの先頭へのポインターを取得します。

```cpp
constexpr pointer data() const noexcept;
```

### <a name="return-value"></a>戻り値

スパンに格納されている最初の項目へのポインター。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    auto i = mySpan.data();
    cout << *i;
}
```

```Output
0
```

## <a name="spandifference_type"></a><a name="difference_type"></a> `span::difference_type`

スパン内の2つの要素間の要素の数。

```cpp
using difference_type = std::ptrdiff_t;
```

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::difference_type distance = mySpan.end() - mySpan.begin();
    cout << distance << std::endl;
}
```

```Output
3
```

## <a name="spanelement_type"></a><a name="element_type"></a> `span::element_type`

スパン内の要素の型。

```cpp
using element_type = T;
```

### <a name="remarks"></a>Remarks

スパンが作成されると、テンプレートパラメーターから型が取得され `T` ます。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::element_type et = mySpan[2];
    cout << et << endl;
}
```

```Output
2
```

## <a name="spanempty"></a><a name="empty"></a> `span::empty`

スパンに要素が含まれているかどうか。

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>戻り値

`true`の場合はを返し `this->size() == 0` ます。 それ以外の場合は `false` を返します。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    bool isEmpty = mySpan.empty(); // isEmpty == false
}
```

## <a name="spanend"></a><a name="end"></a> `span::end`

スパンの末尾までの反復子を取得します。

```cpp
constexpr iterator end() const noexcept;
```

### <a name="return-value"></a>戻り値

スパンの末尾の次の位置を指す反復子。

### <a name="remarks"></a>Remarks

`end` は、反復子が範囲の末尾を超えたかどうかをテストするために使用されます。

この反復子によって返された値を逆参照しないでください。 このメソッドを使用して、反復子がスパン内の最後の要素を超えたかどうかを識別します。

### <a name="example"></a>例

```cpp
// Iteration
for (auto it = s1.begin(); it != s1.end(); ++it)
{
    cout << *it;
}
```

## <a name="spanfirst"></a><a name="first_view"></a> `span::first`

このスパンの前から取得したサブスパンを取得します。

```cpp
constexpr auto first(size_type count) const noexcept;
template <size_t count> constexpr auto first() const noexcept;
```

### <a name="parameters"></a>パラメーター

*数*\
サブスパンに配置する、このスパンの先頭からの要素の数。  
要素の数は、次に示すように、テンプレートまたは関数にパラメーターとして指定します。

### <a name="return-value"></a>戻り値

`count`このスパンの先頭からの要素を格納しているスパン。

### <a name="remarks"></a>Remarks

コンパイル時にを検証し、範囲に関する情報を保持するために、可能な場合は、この関数のテンプレートバージョンを使用し `count` ます。これにより、固定エクステントの範囲が返されます。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto first2 = mySpan.first(2);
    cout << "mySpan.first(2): ";
    for (auto& i : first2)
    {
        cout << i;
    }

    cout << "\nmySpan.first<2>: ";
    auto viewSpan = mySpan.first<2>();
    for (auto& i : viewSpan)
    {
        cout << i;
    }
}
```

```Output
mySpan.first(2): 01
mySpan.first<2>: 01
```

## <a name="spanfront"></a><a name="front"></a> `span::front`

スパン内の最初の要素を取得します。

```cpp
constexpr reference front() const noexcept;
```

### <a name="return-value"></a>戻り値

スパン内の最初の要素への参照。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto i = mySpan.front();
    cout << i;
}
```

```Output
0
```

## <a name="spaniterator"></a><a name="iterator"></a> `span::iterator`

Span 要素に対する反復子の型。

```cpp
using iterator = implementation-defined-iterator-type;
```

### <a name="remarks"></a>Remarks

この型は、スパン内の要素に対する反復子として機能します。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::iterator it = mySpan.begin();
    cout << *it++ << *it++ << *it;
}
```

```Output
012
```

## <a name="spanlast"></a><a name="last_view"></a> `span::last`

このスパンの終了から取得したサブスパンを取得します。

```cpp
constexpr span<element_type, dynamic_extent> last(const size_type count) const noexcept;
template <size_t count> constexpr span<element_type, count> last() const noexcept;
```

### <a name="parameters"></a>パラメーター

*数*\
サブスパンに格納するこのスパンの終了位置の要素の数。
この数値は、次に示すように、テンプレートまたは関数にパラメーターとして指定できます。

### <a name="return-value"></a>戻り値

このスパンの最後の要素を格納しているスパン `count` 。

### <a name="remarks"></a>Remarks

コンパイル時にを検証し、範囲に関する情報を保持するために、可能な場合は、この関数のテンプレートバージョンを使用し `count` ます。これにより、固定エクステントの範囲が返されます。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    auto first2 = mySpan.last(2);
    cout << "mySpan.last(2): ";
    for (auto& i : last2)
    {
        cout << i;
    }

    cout << "\nmySpan.last<2>: ";
    auto viewSpan = mySpan.last<2>();
    for (auto& i : viewSpan)
    {
        cout << i;
    }
}
```

```Output
mySpan.last(2): 12
mySpan.last<2>: 12
```

## <a name="spanoperator"></a><a name="op_at"></a> `span::operator[]`

スパン内の指定した位置にある要素を取得します。

```cpp
constexpr reference operator[](size_type offset) const;
```

### <a name="parameters"></a>パラメーター

*影*\
アクセスするスパン内の0から始まる要素。

### <a name="return-value"></a>戻り値

位置の*オフセット*位置にある要素への参照。 位置が無効な場合、動作は定義されていません。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan[1];
}
```

```Output
1
```

## <a name="spanoperator"></a><a name="op_eq"></a> `span::operator=`

別のスパンをこの1つに割り当てます。

```cpp
constexpr span& operator=(const span& other) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*他の*\
このに割り当てるスパン。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>Remarks

割り当てでは、データポインターとサイズの簡易コピーが行われます。 は、 `span` それに含まれる要素にメモリを割り当てないため、浅いコピーは安全です。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    span<int> mySpan2;
    mySpan2 = mySpan;
    for (auto &i : mySpan2)
    {
        cout << it;
    }
}
```

```Output
012
```

## <a name="spanpointer"></a><a name="pointer"></a> `span::pointer`

Span 要素へのポインターとポインターの型 `const` 。

```cpp
using pointer = T*;
using const_pointer = const T*;
```

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    // pointer
    span<int>::pointer ptr = &mySpan[2];
    *ptr = 9;
    cout << mySpan[2];

    // const pointer
    span<int>::const_pointer cPtr = &mySpan[0];
    // *cPtr = 9; error - const
    cout << *cPtr;
}
```

```Output
90
```

## <a name="spanrbegin"></a><a name="rbegin"></a> `span::rbegin`

このスパンの最後の要素を指す反転反復子を取得します。

```cpp
constexpr reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

反転スパンの先頭を指す反復子。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    for (auto rIt = s1.rbegin(); rIt != s1.rend(); ++rIt)
    {
        cout << *rIt;
    }
}
```

```Output
210
```

## <a name="spanreference"></a><a name="reference"></a> `span::reference`

Span 要素への参照と参照の型 `const` 。

```cpp
using reference = T&;
using const_reference = const T&;
```

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    // reference
    span<int>::reference ref = mySpan[0];
    ref = 9;
    cout << mySpan[0];
    // const reference
    span<int>::const_reference cRef = mySpan[1];
    // cRef = 9; error because const
    cout << cRef;
}
```

```Output
91
```

## <a name="spanrend"></a><a name="rend"></a> `span::rend`

反転スパンの末尾の次の位置を指し示すランダムアクセス反復子を取得します。

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>戻り値

反転されたスパン内の最後の要素の次のプレースホルダーへの反転反復子。つまり、反転されていないスパン内の最初の要素の前のプレースホルダーです。

### <a name="remarks"></a>Remarks

`rend`span [:: end](#end)が span で使用されるのと同様に、反転スパンと共に使用されます。 これを使用して、逆順反復子がスパンの末尾に達したかどうかをテストします。

によって返された値を `rend` 逆参照することはできません。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    for (auto rIt = s1.rbegin(); rIt != s1.rend(); ++rIt)
    {
        cout << *rIt;
    }
}
```

## <a name="spanreverse_iterator"></a><a name="reverse_iterator"></a> `span::reverse_iterator`

スパンの反転反復子の型。

```cpp
using reverse_iterator = std::reverse_iterator<iterator>;
```

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::reverse_iterator rIt = mySpan.rbegin();
    cout << *rIt++ << *rIt++ << *rIt;
}
```

```Output
210
```

## <a name="spansize"></a><a name="size"></a> `span::size`

スパン内の要素の数を取得します。

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>戻り値

スパン内の要素の数。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan.size();
}
```

```Output
3
```

## <a name="spansize_bytes"></a><a name="size_bytes"></a> `span::size_bytes`

スパン内の要素のサイズをバイト単位で取得します。

```cpp
constexpr size_type size_bytes() const noexcept;
```

### <a name="return-value"></a>戻り値

スパン内のすべての要素が占有するバイト数。これは、 `sizeof(element_type)` スパン内の要素の数を乗算した値です。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);
    cout << mySpan.size_bytes(); // 3 elements * 4 (size of an int)
}
```

```Output
12
```

## <a name="spansize_type"></a><a name="size_type"></a> `span::size_type`

スパン内の要素の数を格納するのに適した符号なしの型。

```cpp
using size_type = size_t;
```

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::size_type szType = mySpan.size();
    cout << szType;
}
```

```Output
3
```

## <a name="spanspan"></a><a name="span"></a> `span::span`

`span`コンストラクター.

```cpp
constexpr span() noexcept
requires (Extent == 0 || Extent == dynamic_extent) = default;

template <class It>
constexpr explicit(Extent != dynamic_extent)
span(It first, size_type count) noexcept

template <class It, class End>
constexpr explicit(Extent != dynamic_extent)
span(It first, End last) noexcept(noexcept(last - first))

template <class T, size_t N>
requires (Extent == dynamic_extent || Extent == N) && is_convertible_v<T (*)[], T (*)[]>
constexpr span(array<T, N>& arr) noexcept

template <class T, size_t N>
requires (Extent == dynamic_extent || Extent == N) && is_convertible_v<const T (*)[], T (*)[]>
constexpr span(const array<T, N>& arr) noexcept

template <size_t N>
requires (Extent == dynamic_extent || Extent == N)
constexpr span(type_identity_t<T> (&arr)[N]) noexcept

template <class R>
constexpr explicit(Extent != dynamic_extent)
span(R&& r)

// default copy ctor
constexpr span(const span& other) noexcept = default;

// converting  ctor
template <class T, size_t OtherExtent>
requires (Extent == dynamic_extent || OtherExtent == dynamic_extent ||
              Extent == OtherExtent) && is_convertible_v<T (*)[], T (*)[]>
constexpr explicit(Extent != dynamic_extent && OtherExtent == dynamic_extent)
span(const span<T, OtherExtent>& other) noexcept
```

### <a name="parameters"></a>パラメーター

*→*\
配列からスパンを構築します。

*数*\
スパンに含まれる要素の数。

*まずは*\
スパン内の最初の要素を指す反復子。

*前の*\
スパン内の最後の要素の直後にある反復子。

*非該当*\
スパンに含まれる要素の数。

*他の*\
このスパンのコピーを作成します。

*\r\n\r\n*\
この範囲からスパンを構築します。

### <a name="remarks"></a>Remarks

スパンは、スパン内のオブジェクトのストレージを所有していないため、スパン内のアイテムのストレージを解放しません。

|コンストラクター  | 説明  |
|---------|---------|
|`span()` | 空のスパンを構築します。 テンプレートパラメーターがまたはの場合にのみ、オーバーロードの解決時に考慮 `Extent` され `0` `dynamic_extent` ます。|
|`span(It first, size_type count)` | 反復子の最初の要素からスパンを構築 `count` `first` します。  テンプレートパラメーターがでない場合にのみ、オーバーロードの解決時に考慮さ `Extent` `dynamic_extent` れます。 |
|`span(It first, End last)` | 終了位置に達するまで、反復子の要素からスパンを構築し `first` `last` ます。 テンプレートパラメーターがでない場合にのみ、オーバーロードの解決時に考慮さ `Extent` `dynamic_extent` れます。 `It`はである必要があり `contiguous_iterator` ます。  |
|`span(array<T, N>& arr) noexcept;`<br /><br />`span(const array<T, N>& arr) noexcept;`<br /><br />`span(type_identity_t<element_type> (&arr)[N]) noexcept;` |  `N`指定した配列の要素からスパンを構築します。 テンプレートパラメーターがまたはと等しい場合にのみ、オーバーロード解決時に考慮 `Extent` され `dynamic_extent` `N` ます。 |
|`span(R&& r)` |  範囲からスパンを構築します。 テンプレートパラメーターがでない場合にのみ、オーバーロードの解決に参加 `Extent` `dynamic_extent` します。|
|`span(const span& other)` |  コンパイラによって生成されたコピーコンストラクター。 スパンが要素を保持するためのメモリを割り当てないため、データポインターの簡易コピーは安全です。 |
|`span(const span<OtherElementType, OtherExtent>& s) noexcept;` | 変換コンストラクター: 別のスパンからスパンを構築します。 テンプレートパラメーターがの場合、またはがまたはと等しい場合にのみ、オーバーロードの解決に参加 `Extent` `dynamic_extent` `N` `dynamic_extent` `Extent` します。|

### <a name="example"></a>例

```cpp
#include <span>

using namespace std;

int main()
{
    const int MAX=10;

    int x[MAX];
    for (int i = 0; i < MAX; i++)
    {
        x[i] = i;
    }

    span<int, MAX> span1{ x }; // fixed-size span: compiler error if size of x doesn't match template argument MAX
    span<int> span2{ x }; // size is inferred from x
    span<const int> span3 = span2; // converting constructor
    span<int> span4( span2 ); // copy constructor
}
```

## <a name="spansubspan"></a><a name="sub_view"></a> `span::subspan`

このスパンのサブスパンを取得します。

```cpp
constexpr auto subspan(size_type offset, size_type count = dynamic_extent) const noexcept;

template <size_t offset, size_t count = dynamic_extent>
constexpr auto subspan() const noexcept
```

### <a name="parameters"></a>パラメーター

*数*\
サブスパンに格納する要素の数。 `count`が `dynamic_extent` (既定値) の場合、サブスパンは `offset` このスパンの末尾から最後まで取得されます。

*影*\
サブスパンを開始する、このスパン内の場所です。

### <a name="return-value"></a>戻り値

このスパンのから開始するスパン `offset` 。 要素が含まれてい `count` ます。

### <a name="remarks"></a>Remarks

この関数のテンプレートバージョンを使用すると、コンパイル時にカウントを確認できます。これにより、一定の範囲の範囲を返すことによってスパンに関する情報が保持されます。

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    cout << "mySpan.subspan(1,2): ";
    for (auto& i : mySpan.subspan(1,2))
    {
        cout << i;
    }
    cout << "\nmySpan.subspan<1,2>: ";
    for (auto& i : mySpan.subspan<1,2>())
    {
        cout << i;
    }
    cout << "\nmySpan.subspan<1>: ";
    for (auto& i : mySpan.subspan<1>)
    {
        cout << i;
    }
}
```

```Output
mySpan.subspan(1,2): 12
mySpan.subspan<1,2>: 12
mySpan.subspan<1>: 12
```

## <a name="spanvalue_type"></a><a name="value_type"></a> `span::value_type`

範囲内の要素の型 (またはの条件なし) `const` `volatile` 。

```cpp
using value_type = std::remove_cv_t<T>;
```

### <a name="example"></a>例

```cpp
#include <span>
#include <iostream>

using namespace std;

int main()
{
    int a[] = { 0,1,2 };
    span<int> mySpan(a);

    span<int>::value_type vType = mySpan[2];
    cout << vType;
}
```

```Output
2
```

## <a name="deduction-guides"></a><a name="deduction_guides"></a>控除ガイド

次の推定ガイドがスパンに提供されています。

```cpp
// Allows the extent to be deduced from std::array and C++ built-in arrays

template <class T, size_t Extent>
span(T (&)[Extent]) -> span<T, Extent>;

template <class T, size_t Size>
span(array<T, Size>&) -> span<T, Size>;

template <class T, size_t Size>
span(const array<T, Size>&) -> span<const T, Size>;

// Allows the element type to be deduced from the iterator and the end of the span.
// The iterator must be contiguous

template <contiguous_iterator It, class End>
span(It, End) -> span<remove_reference_t<iter_reference_t<It>>>;

// Allows the element type to be deduced from a range.
// The range must be contiguous

template <ranges::contiguous_range Rng>
span(Rng &&) -> span<remove_reference_t<ranges::range_reference_t<Rng>>>;
```

## <a name="see-also"></a>関連項目

[\<span>](../standard-library/span.md)  
[クラステンプレート引数の推論を使用する方法](https://devblogs.microsoft.com/cppblog/how-to-use-class-template-argument-deduction/)
