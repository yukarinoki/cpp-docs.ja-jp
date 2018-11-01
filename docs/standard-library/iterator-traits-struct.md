---
title: iterator_traits 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator_traits
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
ms.openlocfilehash: 6fe9e2d576afcacc7d014d4f5c920ecab3a83fc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657224"
---
# <a name="iteratortraits-struct"></a>iterator_traits 構造体

反復子に必要なすべての重要な型定義を指定するために使用されるテンプレート ヘルパー構造体。

## <a name="syntax"></a>構文

```cpp
struct iterator_traits {
   typedef typename Iterator::iterator_category iterator_category;
   typedef typename Iterator::value_type value_type;
   typedef typename Iterator::difference_type difference_type;
   typedef difference_type distance_type;
   typedef typename Iterator::pointer pointer;
   typedef typename Iterator::reference reference;
   };
```

## <a name="remarks"></a>Remarks

テンプレート構造体はメンバーの型を定義します。

- `iterator_category`: のシノニム`Iterator::iterator_category`します。

- `value_type`: のシノニム`Iterator::value_type`します。

- `difference_type`: のシノニム`Iterator::difference_type`します。

- `distance_type`: のシノニム `Iterator::difference_type.`

- `pointer`: のシノニム`Iterator::pointer`します。

- `reference`: のシノニム`Iterator::reference`します。

部分的な特殊化は、型のオブジェクト ポインターに関連付けられている重要な型を判断する**型** <strong>\*</strong>または**const 型** <strong>\*</strong>.

この実装では、部分的特殊化を利用しないいくつかのテンプレート関数を利用することもできます。

```cpp
template <class Category, class Type, class Diff>
C _Iter_cat(const iterator<Category, Ty, Diff>&);

template <class Ty>
random_access_iterator_tag _Iter_cat(const Ty *);

template <class Category, class Ty, class Diff>
Ty *val_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
Ty *val_type(const Ty *);

template <class Category, class Ty, class Diff>
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
ptrdiff_t *_Dist_type(const Ty *);
```

これは、同じ型のいくつかをより間接的に決定します。 これらの関数は、関数呼び出しの引数として使用します。 その唯一の目的は、呼び出された関数に、有効なテンプレート クラスのパラメーターを提供することです。

## <a name="example"></a>例

```cpp
// iterator_traits.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <vector>
#include <list>

using namespace std;

template< class it >
void
function( it i1, it i2 )
{
   iterator_traits<it>::iterator_category cat;
   cout << typeid( cat ).name( ) << endl;
   while ( i1 != i2 )
   {
      iterator_traits<it>::value_type x;
      x = *i1;
      cout << x << " ";
      i1++;
   };
   cout << endl;
};

int main( )
{
   vector<char> vc( 10,'a' );
   list<int> li( 10 );
   function( vc.begin( ), vc.end( ) );
   function( li.begin( ), li.end( ) );
}
/* Output:
struct std::random_access_iterator_tag
a a a a a a a a a a
struct std::bidirectional_iterator_tag
0 0 0 0 0 0 0 0 0 0
*/
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<iterator>](../standard-library/iterator.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
