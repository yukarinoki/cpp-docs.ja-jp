---
title: '&lt;numeric&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::partial_sum
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::partial_sum [C++]
ms.openlocfilehash: 6df37cf4f6c8afe09f25550d4fc0d9acb553ac52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236559"
---
# <a name="ltnumericgt-functions"></a>&lt;numeric&gt; 関数

||||
|-|-|-|
|[accumulate](#accumulate)|[adjacent_difference](#adjacent_difference)|[inner_product](#inner_product)|
|[iota](#iota)|[partial_sum](#partial_sum)|

## <a name="accumulate"></a>  accumulate

連続する部分和を計算することで、いくつかの初期値を含め、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を計算します。

```cpp
template <class InputIterator, class Type>
Type accumulate(InputIterator first, InputIterator last, Type val);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type val,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
指定された二項演算に従って、合計または結合される範囲内の先頭の要素を示す入力反復子。

*last*<br/>
指定された二項演算に従って、合計または結合される範囲内の最後の要素、つまり反復処理され累積に実際に含まれる最後の要素の 1 つ次の位置を示す入力反復子。

*val*<br/>
指定された二項演算に従って、各要素がさらに追加または結合される初期値。

*binary_op*<br/>
指定された範囲と、以前の適用の結果の各要素に適用される二項演算。

### <a name="return-value"></a>戻り値

合計*val*の最初のテンプレート関数にして、または 2 つ目のテンプレート関数の指定、sum 操作ではなく、二項演算を適用した結果の指定した範囲内のすべての要素 ( *PartialResult、 \*Iter*) ここで、 *PartialResult*操作の前のアプリケーションの結果と`Iter`が範囲内の要素を指す反復子です。

### <a name="remarks"></a>Remarks

初期値は保証があることを明確に定義された結果の範囲が空で、後者*val*が返されます。 二項演算は結合的または可換的である必要はありません。 結果は初期値に初期化*val*し*結果* =  `binary_op` (*結果*、 <strong>\*</strong>`Iter`) 内で、繰り返しが計算されます、`Iter`が範囲内の連続する要素を指す反復子です。 範囲が有効であることが必要で、複雑さは範囲のサイズに応じて線形的です。 2 項演算子の戻り値の型は、反復中のクロージャを確実にするために、**Type** に変換可能である必要があります。

### <a name="example"></a>例

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a>  adjacent_difference

入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
含まれる要素がそれぞれの先行要素と差分処理されるか、または値のペアが別の指定された二項演算で処理される入力範囲の先頭の要素を示す入力反復子。

*last*<br/>
含まれる要素がそれぞれの先行要素と差分処理されるか、または値のペアが別の指定された二項演算で処理される入力範囲の最後の要素を示す入力反復子。

*結果*<br/>
一連の差分または指定された演算の結果が格納されるターゲット範囲の先頭の要素を示す出力反復子。

*binary_op*<br/>
差分プロシージャの減算演算を置き換える一般的な演算で適用される二項演算。

### <a name="return-value"></a>戻り値

ターゲット範囲の終了位置を示す出力反復子: `result` + ( `last` - `first`)。

### <a name="remarks"></a>Remarks

出力反復子 _*結果*入力反復子と同じ反復子にできる *、* ように`adjacent_difference`インプレース s を計算することがあります。

値のシーケンスの *、* 1、 *、* 2、 *、* 3 の最初のテンプレート関数は、入力の範囲が連続する格納`partial_difference`s *、* 1、 *、* 2 - *、* 1、a3 - *、* ターゲット範囲内の 2。

値のシーケンスの *、* 1、 *、* 2、 *、* 3、2 つ目のテンプレート関数は、入力の範囲内の連続する格納`partial_difference`s *、* 1、 *、* 2 `binary_op` *、* 1、 *、* 3 `binary_op` *、* ターゲット範囲内の 2。

適用される演算の順序は完全に指定されるため、二項演算 `binary_op` は結合的または可換的である必要はありません。

### <a name="example"></a>例

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="inner_product"></a>  inner_product

2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val,
    BinaryOperation1  binary_op1,
    BinaryOperation2  binary_op2);
```

### <a name="parameters"></a>パラメーター

*first1*<br/>
2 番目の範囲との内積または一般化された内積を計算する必要がある、1 番目の範囲内の先頭の要素を示す入力反復子。

*last1*<br/>
2 番目の範囲との内積または一般化された内積を計算する必要がある、1 番目の範囲内の最後の要素を示す入力反復子。

*first2*<br/>
1 番目の範囲との内積または一般化された内積を計算する必要がある、2 番目の範囲内の先頭の要素を示す入力反復子。

*val*<br/>
範囲間の内積または一般化された内積を追加する必要がある初期値。

*binary_op1*<br/>
内積の一般化における要素ごとの内積に適用される内積の合計演算を置き換える二項演算。

*binary_op2*<br/>
内積の一般化における内積の要素ごとの乗算演算を置き換える二項演算。

### <a name="return-value"></a>戻り値

1 番目のメンバー関数は、要素ごとの積の合計を返し、それを指定された初期値に追加します。 したがって、*a*i と *b*i の値の範囲の場合、次を返します。

`val` + ( *、* 1 \* *b*1) + ( *、* 2 \* *b*2) +… + ( *、* n \* *b*n)

反復的*val*で`val`+ ( *、* は\* *b*しました)。

2 番目のメンバー関数は次を返します。

`val` *binary_op1* ( *a*1 *binary_op2* *b*1 ) *binary_op1* ( *a*2 *binary_op2* *b*2 ) *binary_op1* ... *binary_op1* ( *a*n *binary_op2* *b*n )

反復的*val*で`val` *binary_op1* ( *、* は*binary_op2* *b*i)。

### <a name="remarks"></a>Remarks

初期値があることを明確に定義された結果の範囲が空の場合、その場合により、 *val*が返されます。 二項演算は結合的または可換的である必要はありません。 範囲が有効であることが必要で、複雑さは範囲のサイズに応じて線形的です。 2 項演算子の戻り値の型は、反復中のクロージャを確実にするために、**Type** に変換可能である必要があります。

### <a name="example"></a>例

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a>  iota

最初の要素で始まると、一連の値のインクリメントでの入力開始の値を格納します (` value++`) 間隔内の要素の各`[ first,  last)`します。

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
入力する必要がある、範囲内の先頭の要素を示す入力反復子。

*last*<br/>
入力する必要がある、範囲内の最後の要素を示す入力反復子。

*value*<br/>
先頭の要素に格納し、以降の要素に関して連続してインクリメントするための開始値。

### <a name="remarks"></a>Remarks

### <a name="example"></a>例

次の例は、`iota` 関数のいくつかの使用法を示しています。整数の [list](../standard-library/list.md) を入力し、次に、[vector](../standard-library/vector.md) に `list` を入力することで、[random_shuffle](../standard-library/algorithm-functions.md#random_shuffle) 関数を使用できます。

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="partial_sum"></a>  partial_sum

入力範囲の先頭の要素から *i* 番目の要素までの一連の合計を計算し、各合計の結果をターゲット範囲の *i* 番目の要素に格納するか、または合計演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
指定された二項演算に従って、部分的に合計または結合される範囲内の先頭の要素を示す入力反復子。

*last*<br/>
指定された二項演算に従って、部分的に合計または結合される範囲内の最後の要素、つまり反復処理され累積に実際に含まれる最後の要素の 1 つ次の位置を示す入力反復子。

*結果*<br/>
一連の部分和または指定された演算の結果が格納されるターゲット範囲の先頭の要素を示す出力反復子。

*binary_op*<br/>
部分和プロシージャの合計演算を置き換える一般的な演算で適用される二項演算。

### <a name="return-value"></a>戻り値

ターゲット範囲の終了位置を示す出力反復子: `result` + (`last` - `first`)、

### <a name="remarks"></a>Remarks

出力反復子*結果*入力反復子と同じ反復子にできる*最初*、インプレース部分和を計算することがあります。

入力範囲に *a*1、*a*2、*a*3 の値のシーケンスがある場合、最初のテンプレート関数は連続する部分和をターゲット範囲に格納します。ここで、*i* 番目の要素は (  ( ( *a*1 + *a*2) + *a*3) *a*i) によって得られます。

値のシーケンスの *、* 1、 *、* 2、 *、* 3、入力の範囲で 2 つ目のテンプレート関数は、格納、i 番目の要素が、ターゲット範囲内の連続する部分和によって指定された ((( *、* 1 `binary_op` *、* 2) `binary_op` *、* 3) *、* は)。

二項演算*binary_op*結合的または可換かする必要はありませんが、操作の順序を適用するためには完全に指定します。

### <a name="example"></a>例

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="see-also"></a>関連項目

[\<numeric>](../standard-library/numeric.md)<br/>
