---
description: '詳細: pair 構造体'
title: pair 構造体
ms.date: 11/04/2016
f1_keywords:
- utility/std::pair
helpviewer_keywords:
- pair class
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
ms.openlocfilehash: 052dd0e95125726f377e9d74585cfad6cc7e8c0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340815"
---
# <a name="pair-structure"></a>pair 構造体

2 つのオブジェクトを 1 つのオブジェクトとして処理する機能を提供する構造体。

## <a name="syntax"></a>構文

```cpp
struct pair
{
    typedef T1 first_type;
    typedef T2 second_type;
    T1 first;
    T2 second;
    constexpr pair();
    pair(const pair&) = default;
    pair(pair&&) = default;
    constexpr pair(
        const T1& Val1,
        const T2& Val2);

    template <class Other1, class Other2>
    constexpr pair(const pair<Other1, Other2>& Right);

    template <class Other1, class Other2>
    constexpr pair(const pair <Other1 Val1, Other2 Val2>&& Right);

    template <class Other1, class Other2>
    constexpr pair(Other1&& Val1, Other2&& Val2);

    template <class... Args1, class... Args2>
    pair(piecewise_construct_t, tuple<Args1...> first_args, tuple<Args2...> second_args);

    pair& operator=(const pair& p);
    template<class U1, class U2> pair& operator=(const pair<U1, U2>& p);
    pair& operator=(pair&& p) noexcept(see below );
    template<class U1, class U2> pair& operator=(pair<U1, U2>&& p);

    void swap(pair& p) noexcept(see below );
};

template<class T1, class T2>
    pair(T1, T2) -> pair<T1, T2>;
```

### <a name="parameters"></a>パラメーター

*Val1*\
`pair` の最初の要素を初期化する値。

*Val2*\
`pair` の 2 番目の要素を初期化する値。

*そうです*\
別のペアの要素を初期化するために値が使用されるペア。

## <a name="return-value"></a>戻り値

最初の (既定の) コンストラクターは、ペアの最初の要素を既定の型に初期化 `T1` し、2番目の要素を型の既定値に初期化し `T2` ます。  両方の型が既定で構築可能である場合に定義されます。

2番目のコンストラクターは、ペアの最初の要素を *Val1* に初期化し、2番目のコンストラクターを Val2 に初期化し *ます。*  これは、両方の型がコピーによって構築可能である場合に定義されます。

3番目の (テンプレート) コンストラクターは、ペアの最初の要素をに初期化し `Right` ます。 **最初** に、2番目のをにし `Right` ます。 **second**。  これは、指定された値型から両方の型のペアが構築可能である場合に定義されます。

4番目のコンストラクターは、ペアの最初の要素を *Val1* に初期化し、2番目のコンストラクターを [右辺値参照宣言子 ( &&](../cpp/rvalue-reference-declarator-amp-amp.md)) を使用して *Val2* に初期化します。  これは、指定された値型から両方の型のペアが構築可能である場合に定義されます。

## <a name="remarks"></a>解説

テンプレート構造体は、型と型のオブジェクトのペアをそれぞれ格納し `T1` `T2` ます。 型は `first_type` テンプレートパラメーターと同じであり、 `T1` 型は `second_type` テンプレートパラメーターと同じです `T2` 。 `T1` また、 `T2` それぞれのニーズで、既定のコンストラクター、1つの引数を持つコンストラクター、およびデストラクターだけを指定します。 型はとして `pair` ではなくとして宣言されているため、型のすべてのメンバーはパブリックです **`struct`** **`class`** 。 ペアの最も一般的な用途としては、2 つの値を返す関数の戻り値の型としての用途と、連想コンテナー クラスの [map クラス](../standard-library/map-class.md)と [multimap クラス](../standard-library/multimap-class.md)の要素としての用途の 2 つが挙げられます。これらのクラスはどちらも、キーと、各要素に関連付けられている値の型を持っています。 後者は、ペアの連想コンテナーの要件を満たし、フォームの値の型を持ち `pair< const key_type, mapped_type >` ます。

## <a name="example"></a>例

```cpp
// utility_pair.cpp
// compile with: /EHsc
#include <utility>
#include <map>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;

   // Using the constructor to declare and initialize a pair
   pair <int, double> p1 ( 10, 1.1e-2 );

   // Compare using the helper function to declare and initialize a pair
   pair <int, double> p2;
   p2 = make_pair ( 10, 2.22e-1 );

   // Making a copy of a pair
   pair <int, double> p3 ( p1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;

   // Using a pair for a map element
   map <int, int> m1;
   map <int, int>::iterator m1_Iter;

   typedef pair <int, int> Map_Int_Pair;

   m1.insert ( Map_Int_Pair ( 1, 10 ) );
   m1.insert ( Map_Int_Pair ( 2, 20 ) );
   m1.insert ( Map_Int_Pair ( 3, 30 ) );

   cout << "The element pairs of the map m1 are:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " ( " << m1_Iter -> first << ", "
           << m1_Iter -> second << " )";
   cout   << "." << endl;

   // Using pair as a return type for a function
   pair< map<int,int>::iterator, bool > pr1, pr2;
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );

   if( pr1.second == true )
   {
      cout << "The element (4,40) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }

   if( pr2.second == true )
   {
      cout << "The element (1,10) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }
}
```

```Output
The pair p1 is: ( 10, 0.011 ).
The pair p2 is: ( 10, 0.222 ).
The pair p3 is: ( 10, 0.011 ).
The element pairs of the map m1 are: ( 1, 10 ) ( 2, 20 ) ( 3, 30 ).
The element (4,40) was inserted successfully in m1.
The element with a key value of
( (pr2.first) -> first ) = 1 is already in m1,
so the insertion failed.
```
