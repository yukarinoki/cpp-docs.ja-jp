---
title: insert_iterator クラス
ms.date: 11/04/2016
f1_keywords:
- iterator/std::insert_iterator
- iterator/std::insert_iterator::container_type
- iterator/std::insert_iterator::reference
helpviewer_keywords:
- std::insert_iterator [C++]
- std::insert_iterator [C++], container_type
- std::insert_iterator [C++], reference
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
ms.openlocfilehash: 2865db023425fa301ad5440a0dc8ed491213f33f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368056"
---
# <a name="insert_iterator-class"></a>insert_iterator クラス

出力反復子の要件を満たす反復子アダプターについて説明します。 シーケンスに要素を上書きではなく、挿入し、C++ のシーケンスと連想コンテナーの反復子が提供する上書きセマンティクスとは異なるセマンティクスを提供します。 `insert_iterator` クラスは、適合させるコンテナーの型でテンプレート化されます。

## <a name="syntax"></a>構文

```cpp
template <class Container>
class insert_iterator;
```

### <a name="parameters"></a>パラメーター

*コンテナー*\
要素が `insert_iterator` によって挿入されるコンテナーの型。

## <a name="remarks"></a>解説

型`Container`のコンテナーは、可変サイズのコンテナーの要件を満たし、パラメーターが型で、型`Container::iterator``Container::value_type``Container::iterator`を返す 2 つの引数の挿入メンバー関数を持っている必要があります。 C++ 標準ライブラリ シーケンスおよび並べ替えられた連想コンテナーはこれらの要件を満たしており、`insert_iterator` で使用するために適合させることができます。 連想コンテナーでは、位置の引数はヒントとして扱われ、ヒントの品質に応じてパフォーマンスを向上させる場合も、低下させる場合もあります。 `insert_iterator` は、常に、コンテナーで初期化されている必要があります。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[insert_iterator](#insert_iterator)|コンテナーの指定された位置に要素を挿入する `insert_iterator` を構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[container_type](#container_type)|一般的な挿入の対象となるコンテナーを表す型。|
|[参照](#reference)|関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子*](#op_star)|一般的な挿入のための出力反復子式 * `i` = `x` を実装するために使用される逆参照演算子。|
|[演算子++](#op_add_add)|値を格納できる次の位置に `insert_iterator` をインクリメントします。|
|[演算子=](#op_eq)|一般的な挿入のための出力反復子式 * `i` = `x` を実装するために使用される代入演算子。|

## <a name="requirements"></a>必要条件

**ヘッダー** \<: 反復>

**名前空間:** std

## <a name="insert_iteratorcontainer_type"></a><a name="container_type"></a>insert_iterator::container_type

一般的な挿入の対象となるコンテナーを表す型。

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター *Container* のシノニムです。

### <a name="example"></a>例

```cpp
// insert_iterator_container_type.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L1;
   insert_iterator<list<int> >::container_type L2 = L1;
   inserter ( L2, L2.end ( ) ) = 20;
   inserter ( L2, L2.end ( ) ) = 10;
   inserter ( L2, L2.begin ( ) ) = 40;

   list <int>::iterator vIter;
   cout << "The list L2 is: ( ";
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The list L2 is: ( 40 20 10 ).
*/
```

## <a name="insert_iteratorinsert_iterator"></a><a name="insert_iterator"></a>insert_iterator::insert_iterator

コンテナーの指定された位置に要素を挿入する `insert_iterator` を構築します。

```cpp
insert_iterator(Container& _Cont, typename Container::iterator _It);
```

### <a name="parameters"></a>パラメーター

*_Cont*\
`insert_iterator` によって要素が挿入されるコンテナ―です。

*_It*\
挿入の位置。

### <a name="remarks"></a>解説

すべてのコンテナーには、`insert_iterator`によって呼び出される insert メンバー関数があります。 連想コンテナーについては、位置パラメーターは参考にすぎません。 Inserter 関数は、値を挿入する便利な手段となります。

### <a name="example"></a>例

```cpp
// insert_iterator_insert_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 1 ; i < 4 ; ++i )
   {
      L.push_back ( 10 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the member function to insert an element
   inserter ( L, L.begin ( ) ) = 2;

   // Alternatively, you may use the template version
   insert_iterator< list < int> > Iter(L, L.end ( ) );
*Iter = 300;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The list L is:
( 10 20 30 ).
After the insertions, the list L is:
( 2 10 20 30 300 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_star"></a>insert_iterator::演算子*

アドレス指定された要素を返す挿入反復子を逆参照します。

```cpp
insert_iterator<Container>& operator*();
```

### <a name="return-value"></a>戻り値

このメンバー関数は、アドレス指定された要素の値を返します。

### <a name="remarks"></a>解説

出力反復式の**\*反復式の Iter** = **値**を実装するために使用します。 シーケンス`Iter`内の要素をアドレス指定する反復子の場合 = **value****\*、その**要素を Iter 値で置き換え、シーケンス内の要素の総数を変更しません。

### <a name="example"></a>例

```cpp
// insert_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 0 ; i < 4 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The original list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   insert_iterator< list < int> > Iter(L, L.begin ( ) );
*Iter = 10;
*Iter = 20;
*Iter = 30;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The original list L is:
( 0 2 4 6 ).
After the insertions, the list L is:
( 10 20 30 0 2 4 6 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_add_add"></a>insert_iterator:演算子++

値を格納できる次の位置に `insert_iterator` をインクリメントします。

```cpp
insert_iterator<Container>& operator++();

insert_iterator<Container> operator++(int);
```

### <a name="parameters"></a>パラメーター

値を格納できる次の位置をアドレス指定する `insert_iterator`。

### <a name="remarks"></a>解説

preincrementation と postincrementation の演算子は、どちらも同じ結果を返します。

### <a name="example"></a>例

```cpp
// insert_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 5 ; ++i )
   {
      vec.push_back (  i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is:\n ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   insert_iterator<vector<int> > ii ( vec, vec.begin ( ) );
*ii = 30;
   ii++;
*ii = 40;
   ii++;
*ii = 50;

   cout << "After the insertions, the vector vec becomes:\n ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
/* Output:
The vector vec is:
( 1 2 3 4 ).
After the insertions, the vector vec becomes:
( 30 40 50 1 2 3 4 ).
*/
```

## <a name="insert_iteratoroperator"></a><a name="op_eq"></a>insert_iterator::演算子=

コンテナーに値を挿入し、新しい要素を指すように更新された反復子を返します。

```cpp
insert_iterator<Container>& operator=(
    typename Container::const_reference val,);

insert_iterator<Container>& operator=(
    typename Container::value_type&& val);
```

### <a name="parameters"></a>パラメーター

*ヴァル*\
コンテナーに割り当てられる値。

### <a name="return-value"></a>戻り値

コンテナーに挿入される要素への参照。

### <a name="remarks"></a>解説

1 つ目のメンバー演算子は次の評価をします。

`Iter = container->insert(Iter, val)`;

`++Iter;`

その後、`*this` を返します。

2 つ目のメンバー演算子は次の評価をします。

`Iter = container->insert(Iter, std::move(val));`

`++Iter;`

その後、`*this` を返します。

### <a name="example"></a>例

```cpp
// insert_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 0 ; i < 4 ; ++i )
   {
      L.push_back ( 2 * i );
   }

   cout << "The original list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   insert_iterator< list < int> > Iter(L, L.begin ( ) );
*Iter = 10;
*Iter = 20;
*Iter = 30;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
/* Output:
The original list L is:
( 0 2 4 6 ).
After the insertions, the list L is:
( 10 20 30 0 2 4 6 ).
*/
```

## <a name="insert_iteratorreference"></a><a name="reference"></a>insert_iterator::参照

関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。

```cpp
typedef typename Container::reference reference;
```

### <a name="remarks"></a>解説

この型は、関連するコンテナーによって制御されるシーケンスの要素への参照を示します。

### <a name="example"></a>例

```cpp
// insert_iterator_container_reference.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   list<int> L;
   insert_iterator<list<int> > iivIter( L , L.begin ( ) );
*iivIter = 10;
*iivIter = 20;
*iivIter = 30;

   list<int>::iterator LIter;
   cout << "The list L is: ( ";
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++ )
      cout << *LIter << " ";
   cout << ")." << endl;

   insert_iterator<list<int> >::reference
        RefFirst = *(L.begin ( ));
   cout << "The first element in the list L is: "
        << RefFirst << "." << endl;
}
/* Output:
The list L is: ( 10 20 30 ).
The first element in the list L is: 10.
*/
```

## <a name="see-also"></a>関連項目

[\<反復器>](../standard-library/iterator.md)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
