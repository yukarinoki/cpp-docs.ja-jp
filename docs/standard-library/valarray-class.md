---
title: valarray クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::valarray
- valarray/std::valarray::value_type
- valarray/std::valarray::apply
- valarray/std::valarray::cshift
- valarray/std::valarray::free
- valarray/std::valarray::max
- valarray/std::valarray::min
- valarray/std::valarray::resize
- valarray/std::valarray::shift
- valarray/std::valarray::size
- valarray/std::valarray::sum
- valarray/std::valarray::swap
helpviewer_keywords:
- std::valarray [C++]
- std::valarray [C++], value_type
- std::valarray [C++], apply
- std::valarray [C++], cshift
- std::valarray [C++], free
- std::valarray [C++], max
- std::valarray [C++], min
- std::valarray [C++], resize
- std::valarray [C++], shift
- std::valarray [C++], size
- std::valarray [C++], sum
- std::valarray [C++], swap
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
ms.openlocfilehash: abfac363388fc86a8b9c68df149bbe65fdd1d427
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482720"
---
# <a name="valarray-class"></a>valarray クラス

このテンプレート クラスは、型の要素のシーケンスを制御するオブジェクトを表します`Type`配列として格納されている、高速数値演算を実行するために設計された、および計算パフォーマンス用に最適化されたは。

## <a name="remarks"></a>Remarks

このクラスは、順序付けられた値のセットからなる数学的な概念の表現で、要素はゼロから順に番号が付けられます。 このクラスは、[vector](../standard-library/vector-class.md) などのファースト クラスのシーケンス コンテナーがサポートする機能の一部 (すべてではない) をサポートするため、コンテナーによく似たものとして記述されます。 次の 2 つの重要な点で、テンプレート クラス vector とは異なります。

- 定義の対応する要素間の多数の算術演算`valarray<Type>`の同じ型と長さ、オブジェクトなど*xarr* = cos ( *yarr*) + sin ( *zarr*).

- さまざまなサブスクライブするために興味深い方法を定義、`valarray<Type>`オーバー ロードによって、オブジェクト[演算子&#91;&#93;](#op_at)します。

クラスのオブジェクト`Type`:

- 従来の動作で、パブリックな既定のコンストラクター、デストラクター、コピー コンストラクター、および代入演算子が用意されています。

- 従来の動作で、必要に応じて浮動小数点型に対して定義される算術演算子と数学関数を定義します。

特に、コピーによる構築と、代入に先行する既定の構築の間に、微妙な違いはありません。 クラスのオブジェクトに対する操作のいずれも`Type`例外をスローする可能性があります。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[valarray](#valarray)|特定のサイズの、または特定の値の要素を持つ `valarray` を構築します。また、他の `valarray` のコピーやサブセットとして `valarray` を構築します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[value_type](#value_type)|`valarray` 内に格納された要素の型を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[apply](#apply)|`valarray` 内の各要素に対して指定された関数を適用します。|
|[cshift](#cshift)|指定された位置数で、`valarray` 内のすべての要素を周期的にシフトします。|
|[free](#free)|`valarray` によって使用されるメモリを解放します。|
|[max](#max)|`valarray` 内の最大要素を検索します。|
|[min](#min)|`valarray` 内の最小要素を検索します。|
|[resize](#resize)|必要に応じて要素を追加または削除して、`valarray` 内の要素数を指定された数に変更します。|
|[shift](#shift)|`valarray` 内のすべての要素を指定された位置数だけシフトします。|
|[size](#size)|`valarray` 内の要素数を検索します。|
|[sum](#sum)|`valarray` 内にある長さが 0 以外の要素すべての合計を求めます。|
|[swap](#swap)||

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!](#op_not)|`valarray` 内の各要素の論理 `NOT` 値を取得する、単項演算子。|
|[operator%=](#op_mod_eq)|指定された `valarray` または要素型の値で配列の要素を要素ごとに除算した剰余を取得します。|
|[operator&=](#op_amp_eq)|配列内の要素のビットごとの `AND` を、指定された `valarray` 内の対応する要素か要素型の値と共に取得します。|
|[operator>>=](#op_gt_gt_eq)|`valarray` オペランドの各要素のビットを、指定された位置数だけ右にシフトさせるか、2 番目の `valarray` で指定された要素ごとの量だけ右にシフトさせます。|
|[operator<<=](#op_lt_lt_eq)|`valarray` オペランドの各要素のビットを、指定された位置数だけ左にシフトさせるか、2 番目の `valarray` で指定された要素ごとの量だけ左にシフトさせます。|
|[operator*=](#op_star_eq)|指定された `valarray` の要素か要素型の値を、要素ごとにオペランド `valarray` に対して乗算します。|
|[operator+](#op_add)|`valarray` 内の各要素に正符号を適用する単項演算子。|
|[operator+=](#op_add_eq)|指定された `valarray` の要素か要素型の値を、要素ごとにオペランド `valarray` に対して加算します。|
|[operator-](#operator-)|`valarray` 内の各要素に負符号を適用する単項演算子。|
|[operator-=](#operator-_eq)|指定された `valarray` の要素か要素型の値を、要素ごとにオペランド `valarray` から減算します。|
|[operator/=](#op_div_eq)|オペランド `valarray` を、指定された `valarray` の要素か要素型の値で要素ごとに除算します。|
|[operator=](#op_eq)|値が直接指定されているか、または他の `valarray` か `slice_array`、`gslice_array`、`mask_array`、や `indirect_array` の一部として値が指定されている `valarray` に要素を代入します。|
|[operator&#91;&#93;](#op_at)|指定されたインデックスまたは指定されたサブセットにある、要素またはその値への参照を返します。|
|[operator^=](#op_xor_eq)|配列と、指定された valarray か要素型の値のどちらか一方との間で行われた、要素ごとの排他的論理 OR 演算子 (`XOR`) を取得します。|
|[operator&#124;=](#op_or_eq)|配列内の要素のビットごとの `OR` を、指定された `valarray` 内の対応する要素か要素型の値と共に取得します。|
|[operator~](#op_dtor)|`valarray` 内の各要素のビットごとの `NOT` 値を取得する単項演算子。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="apply"></a>  valarray::apply

valarray 内の各要素に対して、指定された関数を適用します。

```cpp
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```

### <a name="parameters"></a>パラメーター

*_Func(Type)*<br/>
オペランド valarray の各要素に適用する関数オブジェクト。

*_Func(const Type&)*<br/>
オペランド valarray の各要素に適用する const の関数オブジェクト。

### <a name="return-value"></a>戻り値

オペランド valarray の要素に対して `_Func` を要素ごとに適用した結果である要素から成る valarray。

### <a name="remarks"></a>Remarks

このメンバー関数は、クラスのオブジェクトを返します[valarray](../standard-library/valarray-class.md)**\<型 >**、長さの[サイズ](#size)、その各要素の*は*は`_Func((*this)[I])`します。

### <a name="example"></a>例

```cpp
// valarray_apply.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

using namespace std;

int __cdecl MyApplyFunc( int n )
{
   return n*2;
}

int main( int argc, char* argv[] )
{
   valarray<int> vaR(10), vaApplied(10);
   int i;

   for ( i = 0; i < 10; i += 3 )
      vaR[i] = i;

   for ( i = 1; i < 10; i += 3 )
      vaR[i] = 0;

   for ( i = 2; i < 10; i += 3 )
      vaR[i] = -i;

   cout << "The initial Right valarray is: (";
   for   ( i=0; i < 10; ++i )
      cout << " " << vaR[i];
   cout << " )" << endl;

   vaApplied = vaR.apply( MyApplyFunc );

   cout << "The element-by-element result of "
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";
   for ( i = 0; i < 10; ++i )
      cout << " " << vaApplied[i];
   cout << " )" << endl;
}
/* Output:
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )
The element-by-element result of applying MyApplyFunc to vaR is the
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )
*/
```

## <a name="cshift"></a>  valarray::cshift

指定された位置数で、valarray 内のすべての要素を循環的にシフトします。

```cpp
valarray<Type> cshift(int count) const;
```

### <a name="parameters"></a>パラメーター

*count*<br/>
要素を前方向へシフトする位置数。

### <a name="return-value"></a>戻り値

すべての要素が移動されていますが、新しい valarray*カウント*オペランド valarray 内の位置の左方向、valarray の前方向へ循環的に位置します。

### <a name="remarks"></a>Remarks

正の値を*カウント*要素を左方向へ循環的にシフト*カウント*を配置します。

負の値を*カウント*要素の右方向へ循環的にシフト*カウント*を配置します。

### <a name="example"></a>例

```cpp
// valarray_cshift.cpp
// compile with: /EHsc

#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    valarray<int> va1(10), va2(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;
    for (i = 0; i < 10; i+=1)
        va2[i] = 10 - i;

    cout << "The operand valarray va1 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    // A positive parameter shifts elements right
    va1 = va1.cshift(4);
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    cout << "The operand valarray va2 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;

    // A negative parameter shifts elements left
    va2 = va2.cshift(-4);
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;
}
/* Output:
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)
The cyclically shifted valarray va1 is:
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)
The cyclically shifted valarray va2 is:
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)
*/
```

## <a name="free"></a>  valarray::free

valarray によって使用されるメモリを解放します。

```cpp
void free();
```

### <a name="remarks"></a>Remarks

この非標準の関数は、空の valarray を割り当てることと同じです。 例えば:

```cpp
valarray<T> v;
v = valarray<T>();

// equivalent to v.free()
```

## <a name="max"></a>  valarray::max

valarray 内の最大要素を検索します。

```cpp
Type max() const;
```

### <a name="return-value"></a>戻り値

オペランド valarray の要素の最大値。

### <a name="remarks"></a>Remarks

メンバー関数は、適用することで値を比較する**演算子\<** または**演算子 >** クラスの要素のペア間`Type`、どの演算子は、要素の提供する必要があります`Type`.

### <a name="example"></a>例

```cpp
// valarray_max.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MaxValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i - 1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  10 - i;

   cout << "The operand valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MaxValue = vaR.max (  );
   cout << "The largest element in the valarray is: "
        << MaxValue  << "." << endl;
}
/* Output:
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).
The largest element in the valarray is: 13.
*/
```

## <a name="min"></a>  valarray::min

valarray 内の最小要素を検索します。

```cpp
Type min() const;
```

### <a name="return-value"></a>戻り値

オペランド valarray の要素の最小値。

### <a name="remarks"></a>Remarks

メンバー関数は、適用することで値を比較する**演算子\<** または**演算子 >** クラスの要素のペア間`Type`、どの演算子は、要素の提供する必要があります`Type`.

### <a name="example"></a>例

```cpp
// valarray_min.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MinValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  5 - i;

   cout << "The operand valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MinValue = vaR.min ( );
   cout << "The smallest element in the valarray is: "
        << MinValue  << "." << endl;
}
/* Output:
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).
The smallest element in the valarray is: -9.
*/
```

## <a name="op_not"></a>  valarray::operator!

valarray 内の各要素の論理 **NOT** 値を取得する、単項演算子。

```cpp
valarray<bool> operator!() const;
```

### <a name="return-value"></a>戻り値

オペランド valarray の要素の値の否定であるブール値から成る valarray。

### <a name="remarks"></a>Remarks

論理演算 **NOT** は要素を否定します。これはすべてのゼロを 1 に変換し、すべての非ゼロ値を 1 と見なしてそれをゼロに変換するからです。 ブール値から成る返される valarray は、オペランド valarray と同じサイズです。

ありますが、ビット演算も**いない**[valarray::operator ~](#op_dtor)のバイナリ表現内の個々 のビットのレベルで否定**char**と**int** valarray の要素。

### <a name="example"></a>例

```cpp
// valarray_op_lognot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<bool> vaNOT ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaNOT = !vaL;
   cout << "The element-by-element result of "
        << "the logical NOT operator! is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The element-by-element result of the logical NOT operator! is the
valarray: ( 1 1 1 0 1 0 1 0 1 0 ).
*/
```

## <a name="op_mod_eq"></a>  valarray::operator%=

指定された valarray または要素型の値で配列の要素を要素ごとに除算した剰余を取得します。

```cpp
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray を要素ごとに除算する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

オペランド valarray の要素ごとの除算の剰余要素を持つ valarray を*右*

### <a name="example"></a>例

```cpp
// valarray_class_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL %= vaR;
   cout << "The remainders from the element-by-element "
        << "division is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 53 -67 53 -67 53 -67 ).
The initial  right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
*/
```

## <a name="and_eq"></a>  valarray::operator&amp;=

配列内の要素と、指定された valarray の対応する要素か要素型の値のどちらか一方とのビット演算 **AND** を取得します。

```cpp
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
Valarray または要素型の結合するオペランド valarray と同一で、論理により、要素ごとの値`AND`オペランド valarray とします。

### <a name="return-value"></a>戻り値

要素ごとの要素を持つ valarray 論理`AND`によってオペランド valarray と valarray の*右*

### <a name="remarks"></a>Remarks

ビットごとの演算は、ビットを操作にのみ使用できます**char**と**int**データ型とバリアントできません**float**、**二重**、 **longdouble**、 **void**、 **bool**、またはその他より複雑なデータ型。

ビットごとの AND が、論理と同じ真理値表`AND`のビットごとのレベルでのデータ型に適用されます。 ビット*b*1 と*b*2、 *b*1 `AND` *b*2 は**true**両方のビットが true である場合**false**少なくとも 1 つが false の場合。

### <a name="example"></a>例

```cpp
// valarray_class_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL &= vaR;
   cout << "The element-by-element result of "
        << "the logical AND operator&= is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&= is the
valarray: ( 0 0 0 2 0 4 0 6 0 8 ).
*/
```

## <a name="op_gt_gt_eq"></a>  valarray::operator&gt;&gt;=

valarray オペランドの各要素のビットを、指定された位置数だけ右にシフトさせるか、2 番目の valarray で指定された要素ごとの量だけ右にシフトさせます。

```cpp
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
右シフトの量を示す値か、要素ごとの右シフトの量を示す要素から成る valarray。

### <a name="return-value"></a>戻り値

右で指定した量にシフトした要素の valarray*右*します。

### <a name="remarks"></a>Remarks

符号付きの数値の符号は保持されます。

### <a name="example"></a>例

```cpp
// valarray_class_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL >>= vaR;
   cout << "The element-by-element result of "
        << "the right shift is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*/
```

## <a name="op_lt_lt_eq"></a>  valarray::operator&lt;&lt;=

valarray オペランドの各要素のビットを、指定された位置数だけ左にシフトさせるか、2 番目の valarray で指定された要素ごとの量だけ左にシフトさせます。

```cpp
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
左シフトの量を示す値か、要素ごとの左シフトの量を示す要素から成る valarray。

### <a name="return-value"></a>戻り値

シフトした要素を持つ valarray で指定された量のまま*右*します。

### <a name="remarks"></a>Remarks

符号付きの数値の符号は保持されます。

### <a name="example"></a>例

```cpp
// valarray_class_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL <<= vaR;
   cout << "The element-by-element result of "
        << "the left shift"
        << endl << "on the operand array is the valarray:"
        << endl << "( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift
on the operand array is the valarray:
( 1 -2 4 -8 16 -32 64 -128 ).
*/
```

## <a name="op_star_eq"></a>  valarray::operator*=

指定された valarray の要素か要素型の値を、要素ごとにオペランド valarray に対して乗算します。

```cpp
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray に対して要素ごとに乗算する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

オペランド valarray の要素ごとの製品要素を持つ valarray と*右*します。

### <a name="example"></a>例

```cpp
// valarray_op_emult.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL *= vaR;
   cout << "The element-by-element result of "
        << "the multiplication is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*/
```

## <a name="op_add"></a>  valarray::operator+

valarray 内の各要素に正符号を適用する単項演算子。

```cpp
valarray<Type> operator+() const;
```

### <a name="return-value"></a>戻り値

オペランド配列の要素に正符号を適用した要素から成る valarray。

### <a name="example"></a>例

```cpp
// valarray_op_eplus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaPLUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaPLUS = +vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaPLUS [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
*/
```

## <a name="op_add_eq"></a>  valarray::operator+=

指定された valarray の要素か要素型の値を、要素ごとにオペランド valarray に対して加算します。

```cpp
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray に対して要素ごとに加算する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

オペランド valarray と valarray の要素ごとの合計要素を持つ valarray と*右*します。

### <a name="example"></a>例

```cpp
// valarray_op_eadd.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL += vaR;
   cout << "The element-by-element result of "
        << "the sum is the"
        << endl << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
*/
```

## <a name="valarray__operator-"></a>  valarray::operator-

valarray 内の各要素に負符号を適用する単項演算子。

```cpp
valarray<Type> operator-() const;
```

### <a name="return-value"></a>戻り値

オペランド配列の要素に負符号を適用した要素から成る valarray。

### <a name="example"></a>例

```cpp
// valarray_op_eminus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaMINUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaMINUS = -vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaMINUS [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).
*/
```

## <a name="valarray__operator-_eq"></a>  valarray::operator-=

指定された valarray の要素か要素型の値を、要素ごとにオペランド valarray から減算します。

```cpp
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray から要素ごとに減算する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

オペランド valarray と valarray の要素ごとの差要素を持つ valarray と*右*します。

### <a name="example"></a>例

```cpp
// valarray_op_esub.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL -= vaR;
   cout << "The element-by-element result of "
        << "the difference is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*/
```

## <a name="op_div_eq"></a>  valarray::operator/=

オペランド valarray を、指定された valarray の要素か要素型の値で要素ごとに除算します。

```cpp
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray を要素ごとに除算する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

オペランド valarray の要素ごとの商要素を持つ valarray を除算*右*します。

### <a name="example"></a>例

```cpp
// valarray_op_ediv.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL /= vaR;
   cout << "The element-by-element result of "
        << "the quotient is the"
        << endl << "valarray: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*/
```

## <a name="op_eq"></a>  valarray::operator=

valarray に要素を代入します。その値は、直接、または他の valarray の一部として指定することも、slice_array、gslice_array、mask_array、または indirect_array で指定することもできます。

```cpp
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray にコピーされる valarray。

*val*<br/>
オペランド valarray の要素に代入される値。

*_Slicearray*<br/>
オペランド valarray にコピーされる slice_array。

*_Gslicearray*<br/>
オペランド valarray にコピーされる gslice_array。

*_Maskarray*<br/>
オペランド valarray にコピーされる mask_array。

*_Indarray*<br/>
オペランド valarray にコピーされる indirect_array。

### <a name="return-value"></a>戻り値

最初のメンバー演算子は、によって制御されるシーケンスのコピーで、被制御シーケンスを置き換えます*右*します。

2 番目のメンバー演算子は最初のものと同じですが、[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md) を使用します。

3 番目のメンバー演算子は、のコピーで、被制御シーケンスの各要素を置き換えます*val*します。

残りのメンバー演算子は、制御されるシーケンスの、それぞれの引数で選択される要素を置き換えます。これらの演算子は [operator&#91;&#93;](#op_at) によってのみ生成されます。

置換によって制御されるシーケンスのメンバーの値が、最初の制御されるシーケンスのメンバーに依存する場合、結果は未定義です。

### <a name="remarks"></a>Remarks

制御されるシーケンスの長さが変化する場合、結果は一般に未定義です。 しかし、この実装における影響は、制御されるシーケンスの要素へのポインターまたは参照が無効になることだけです。

### <a name="example"></a>例

```cpp
// valarray_op_assign.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va [ i ] = i;
   for ( i = 0 ; i < 10 ; i+=1 )
      vaR [ i ] = 10 -  i;

   cout << "The operand valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   cout << "The operand valarray vaR is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << vaR [ i ];
   cout << endl;

   // Assigning vaR to va with the first member functon
   va = vaR;
   cout << "The reassigned valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   // Assigning elements of value 10 to va
   // with the second member functon
   va = 10;
   cout << "The reassigned valarray va is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << va [ i ];
   cout << endl;
}
/* Output:
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10
*/
```

## <a name="op_at"></a>  valarray::operator[]

指定されたインデックスまたは指定されたサブセットにある、要素またはその値への参照を返します。

```cpp
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;

valarray<Type> operator[](slice _Slice) const;

valarray<Type> operator[](const gslice& _Gslicearray) const;

valarray<Type> operator[](const valarray<bool>& _Boolarray) const;

valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```

### <a name="parameters"></a>パラメーター

*_Off*<br/>
値を代入する要素のインデックス。

*_Slicearray*<br/>
選択される、または新しい valarray に返されるサブセットを指定する、valarray の slice_array。

*_Gslicearray*<br/>
選択される、または新しい valarray に返されるサブセットを指定する、valarray の gslice_array。

*_Boolarray*<br/>
選択される、または新しい valarray に返されるサブセットを指定する、valarray の bool_array。

*_Indarray*<br/>
選択される、または新しい valarray に返されるサブセットを指定する、valarray の indirect_array。

### <a name="return-value"></a>戻り値

指定されたインデックスまたは指定されたサブセットにある、要素またはその値への参照。

### <a name="remarks"></a>Remarks

によって制御されるものの中から要素のシーケンスを選択するいくつかの方法を提供するメンバー演算子はオーバー ロード<strong>\*この</strong>します。 5 つのメンバー演算子の最初のグループは、[operator=](#op_eq) (および他の代入演算子) のさまざまなオーバーロードと共に機能し、制御されるシーケンスの選択的置換 (スライス) を可能にします。 選択された要素は存在していなければなりません。

1 または 2 に定義された [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) を使用してコンパイルすると、valarray の境界外の要素にアクセスしようとした場合にランタイム エラーが発生します。  詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」を参照してください。

### <a name="example"></a>例

演算子の宣言と使用の方法を示す例については、[slice::slice](../standard-library/slice-class.md#slice) と [gslice::gslice](../standard-library/gslice-class.md#gslice) の例を参照してください。

## <a name="op_xor_eq"></a>  valarray::operator^=

配列と、指定された valarray か要素型の値のどちらか一方との間で行われた、要素ごとの排他的論理 OR 演算子 (**XOR**) を取得します。

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray との排他的論理 **XOR** により要素ごとに結合する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

、要素ごとの排他的論理要素を持つ valarray **XOR**オペランド valarray と*右*。

### <a name="remarks"></a>Remarks

排他的論理 OR (**XOR** という) には次のセマンティクスがあります。要素 *e*1 と *e*2 がある場合、どちらか一方の要素だけが true であるなら、*e*1 **XOR** *e*2 は **true** です。両方の要素が false または両方の要素が true の場合は **false** です。

### <a name="example"></a>例

```cpp
// valarray_op_exor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;

    valarray<int> vaL ( 10 ), vaR ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL [ i ] =  1;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL [ i ] =  0;
    for ( i = 0 ; i < 10 ; i += 3 )
        vaR [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 3 )
        vaR [ i ] =  i-1;
    for ( i = 2 ; i < 10 ; i += 3 )
        vaR [ i ] =  i-1;

    cout << "The initial operand valarray is:  ( ";
        for (i = 0 ; i < 10 ; i++ )
            cout << vaL [ i ] << " ";
    cout << ")." << endl;

    cout << "The  right valarray is: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaR [ i ] << " ";
    cout << ")." << endl;

    vaL ^= vaR;
    cout << "The element-by-element result of "
        << "the bitwise XOR operator^= is the"
        << endl << "valarray: ( ";
        for (i = 0 ; i < 10 ; i++ )
            cout << vaL [ i ] << " ";
    cout << ")." << endl;
}
/* Output:
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^= is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*/
```

## <a name="op_or_eq"></a>  valarray::operator&#124;=

配列内の要素と、指定された valarray の対応する要素か要素型の値のどちらか一方とのビット演算 `OR` を取得します。

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
オペランド valarray とのビット演算 `OR` により要素ごとに結合する、valarray、またはオペランド valarray と同一の要素型の値。

### <a name="return-value"></a>戻り値

ビット演算が、要素ごとの要素が valarray`OR`によってオペランド valarray と valarray の*右*します。

### <a name="remarks"></a>Remarks

ビットごとの演算は、ビットを操作にのみ使用できます**char**と**int**データ型とバリアントできません**float**、**二重**、 **longdouble**、 **void**、 **bool**、またはその他より複雑なデータ型。

ビット演算 `OR` は論理 `OR` と同じ真理値表を持ちますが、個々のビットのレベルでデータ型に適用されます。 ビット *b*1 と *b*2 があり、最低 1 つのビットが true の場合、*b*1 `OR` *b*2 は **true** です。どちらのビットも false の場合は **false** になります。

### <a name="example"></a>例

```cpp
// valarray_class_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial operand valarray is:"
        << endl << "( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is:"
        << endl << "( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL |= vaR;
   cout << "The element-by-element result of "
        << "the logical OR"
        << endl << "operator|= is the valarray:"
        << endl << "( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is:
( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is:
( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the logical OR
operator|= is the valarray:
( 1 0 1 3 3 4 7 6 7 9 ).
*/
```

## <a name="op_dtor"></a>  valarray::operator~

ビット演算を取得する単項演算子`NOT`valarray 内の各要素の値。

```cpp
valarray<Type> operator~() const;
```

### <a name="return-value"></a>戻り値

ビットごとのブール値の valarray`NOT`のオペランド valarray と valarray の要素の値。

### <a name="remarks"></a>Remarks

ビットごとの演算は、ビットを操作にのみ使用できます**char**と**int**データ型とバリアントできません**float**、**二重**、 **longdouble**、 **void**、 **bool**またはその他より複雑なデータ型。

ビット演算 `NOT` は論理 `NOT` と同じ真理値表を持ちますが、個々のビットのレベルでデータ型に適用されます。 ビット *b* がある場合、*b* が false なら、~ *b* は true です。*b* が true なら false になります。 論理**いない**[演算子。](#op_not) カウントのすべての非ゼロ値を要素レベルで適用される**true**、され、結果はブール値の valarray。 ビット演算`NOToperator~`、これに対し、0 または 1 のビットごとの演算の結果に応じて、以外の値を含む valarray になることができます。

### <a name="example"></a>例

```cpp
// valarray_op_bitnot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;

    valarray<unsigned short int> vaL1 ( 10 );
    valarray<unsigned short int> vaNOT1 ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL1 [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL1 [ i ] =  5*i;

    cout << "The initial valarray <unsigned short int> is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaL1 [ i ] << " ";
    cout << ")." << endl;

    vaNOT1 = ~vaL1;
    cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT1 [ i ] << " ";
    cout << ")." << endl << endl;

    valarray<int> vaL2 ( 10 );
    valarray<int> vaNOT2 ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL2 [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL2 [ i ] =  -2 * i;

    cout << "The initial valarray <int> is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaL2 [ i ] << " ";
    cout << ")." << endl;

    vaNOT2 = ~vaL2;
    cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT2 [ i ] << " ";
    cout << ")." << endl;

    // The negative numbers are represented using
    // the two's complement approach, so adding one
    // to the flipped bits returns the negative elements
    vaNOT2 = vaNOT2 + 1;
    cout << "The element-by-element result of "
        << "adding one"
        << endl << "is the negative of the "
        << "original elements the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT2 [ i ] << " ";
    cout << ")." << endl;
}

/* Output:
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).

The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).
The element-by-element result of adding one
is the negative of the original elements the
valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).
*/
```

## <a name="resize"></a>  valarray::resize

valarray 内の要素の数を指定された数に変更します。

```cpp
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,
    const Type val);
```

### <a name="parameters"></a>パラメーター

*_Newsize*<br/>
サイズ変更後の valarray 内の要素の数。

*val*<br/>
サイズ変更後の valarray の要素に与えられる値。

### <a name="remarks"></a>Remarks

1 つ目のメンバー関数は、既定のコンストラクターを使用して要素を初期化します。

制御されるシーケンス内の要素へのすべてのポインターまたは参照は無効になります。

### <a name="example"></a>例

valarray::resize メンバー関数の使用例を次に示します。

```cpp
// valarray_resize.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, sizeNew;

    valarray<int> va1(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;

    cout << "The valarray contains ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray is: "
         << size1  << "." <<endl << endl;

    va1.resize(15, 10);

    cout << "The valarray contains ( ";
        for (i = 0; i < 15; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;
    sizeNew = va1.size();
    cout << "The number of elements in the resized valarray is: "
         << sizeNew  << "." <<endl << endl;
}
```

```Output
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray is: 10.

The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).
The number of elements in the resized valarray is: 15.
```

## <a name="shift"></a>  valarray::shift

valarray 内のすべての要素を指定された位置数だけシフトします。

```cpp
valarray<Type> shift(int count) const;
```

### <a name="parameters"></a>パラメーター

*count*<br/>
要素を前方向へシフトする位置数。

### <a name="return-value"></a>戻り値

すべての要素が移動されていますが、新しい valarray*カウント*オペランド valarray 内の位置の左方向、valarray の前に位置します。

### <a name="remarks"></a>Remarks

正の値を*カウント*要素を左にシフト*カウント*、ゼロ埋め込みが配置されます。

負の値を*カウント*要素の右にシフト*カウント*、ゼロ埋め込みが配置されます。

### <a name="example"></a>例

```cpp
// valarray_shift.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va1 ( 10 ), va2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va1 [ i ] =  i;
   for ( i = 0 ; i < 10 ; i += 1 )
      va2 [ i ] = 10 -  i;

   cout << "The operand valarray va1(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   // A positive parameter shifts elements left
   va1 = va1.shift ( 4 );
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   cout << "The operand valarray va2(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;

   // A negative parameter shifts elements right
   va2 = va2.shift ( - 4 );
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).
*/
```

## <a name="size"></a>  valarray::size

valarray 内の要素の数を調べます。

```cpp
size_t size() const;
```

### <a name="return-value"></a>戻り値

オペランド valarray 内の要素の数。

### <a name="example"></a>例

valarray::size メンバー関数の使用例を次に示します。

```cpp
// valarray_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, size2;

    valarray<int> va1(10), va2(12);
    for (i = 0; i < 10; i += 1)
        va1[i] =  i;
    for (i = 0; i < 10; i += 1)
        va2[i] =  i;

    cout << "The operand valarray va1(10) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray va1 is: va1.size = "
         << size1  << "." <<endl << endl;

    cout << "The operand valarray va2(12) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;

    size2 = va2.size();
    cout << "The number of elements in the valarray va2 is: va2.size = "
         << size2  << "." << endl << endl;

    // Initializing two more elements to va2
    va2[10] = 10;
    va2[11] = 11;
    cout << "After initializing two more elements,\n"
         << "the operand valarray va2(12) is now: ( ";
        for (i = 0; i < 12; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;
    cout << "The number of elements in the valarray va2 is still: "
         << size2  << "." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va1 is: va1.size = 10.

The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va2 is: va2.size = 12.

After initializing two more elements,
the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).
The number of elements in the valarray va2 is still: 12.
```

## <a name="sum"></a>  valarray::sum

valarray 内にある長さが 0 以外の要素すべての合計を求めます。

```cpp
Type sum() const;
```

### <a name="return-value"></a>戻り値

オペランド valarray の要素の合計。

### <a name="remarks"></a>Remarks

メンバー関数が、適用することで、合計に値を追加、長さが 1 よりも大きい場合は、`operator+=`クラスの要素のペア間`Type`、演算子をその結果、必要がありますを指定する型の要素に対して`Type`します。

### <a name="example"></a>例

```cpp
// valarray_sum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    int sumva = 0;

    valarray<int> va ( 10 );
    for ( i = 0 ; i < 10 ; i+=1 )
        va [ i ] =  i;

    cout << "The operand valarray va (10) is: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;

    sumva = va.sum ( );
    cout << "The sum of elements in the valarray is: "
        << sumva  << "." <<endl;
}
/* Output:
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The sum of elements in the valarray is: 45.
*/
```

## <a name="swap"></a>  valarray::swap

2 つの `valarray` の要素を交換します。

```cpp
void swap(valarray& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*right*|交換する要素を提供する `valarray`。|

### <a name="remarks"></a>Remarks

メンバー関数は、交換の間で被制御シーケンス`*this`と*右*します。 この処理は一定時間に実行されます。例外がスローされることはなく、参照や、ポインター、2 つの被制御シーケンス内の要素を指定する反復子が無効にされることもありません。

## <a name="valarray"></a>  valarray::valarray

特定のサイズの valarray や特定の値の要素を持つ valarray を構築します。また、他の valarray のコピーやサブセットとして valarray を構築します。

```cpp
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,
    size_t Count);

valarray(
    const Type* Ptr,
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```

### <a name="parameters"></a>パラメーター

*カウント*<br/>
valarray 内の要素の数。

*val*<br/>
valarray 内の要素の初期化に使用する値。

*ptr*<br/>
valarray 内の要素の初期化に使用する値へのポインター。

*右*<br/>
新しい valarray を初期化するための既存の valarray。

*SliceArray*<br/>
構築する valarray の要素の初期化に使用される要素の値を持つ slice_array。

*GsliceArray*<br/>
構築する valarray の要素の初期化に使用される要素の値を持つ gslice_array。

*MaskArray*<br/>
構築する valarray の要素の初期化に使用される要素の値を持つ mask_array。

*IndArray*<br/>
構築する valarray の要素の初期化に使用される要素の値を持つ indirect_array。

*IList*<br/>
コピーする要素を含む initializer_list。

### <a name="remarks"></a>Remarks

最初の (既定の) コンストラクターは、オブジェクトを空の配列に初期化します。 次の 3 つのコンス トラクターの配列にオブジェクトを初期化する*カウント*要素として次のとおりです。

- 明示的な `valarray(size_t Count)` の場合、各要素は既定のコンストラクターで初期化されます。

- `valarray(const Type& Val, Count)`の各要素が初期化される*Val*します。

- `valarray(const Type* Ptr, Count)` の場合、位置 `I` にある要素が `Ptr`[`I`] で初期化されます。

他の各コンストラクターは、オブジェクトを、引数に指定されたサブセットによって決定される valarray\<Type> オブジェクトに初期化します。

最後のコンストラクターは、その前に示したコンストラクターと同じですが、[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md) を使用します。

### <a name="example"></a>例

```cpp
// valarray_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    // The second member function
    valarray<int> va(10);
    for (auto i : va){
        va[i] = 2 * (i + 1);
    }

    cout << "The operand valarray va is:\n(";
    for (auto i : va) {
        cout << " " << va[i];
    }
    cout << " )" << endl;

    slice Slice(2, 4, 3);

    // The fifth member function
    valarray<int> vaSlice = va[Slice];

    cout << "The new valarray initialized from the slice is vaSlice =\n"
        << "va[slice( 2, 4, 3)] = (";
    for (int i = 0; i < 3; i++) {
        cout << " " << vaSlice[i];
    }
    cout << " )" << endl;

    valarray<int> va2{{ 1, 2, 3, 4 }};
    for (auto& v : va2) {
        cout << v << " ";
    }
    cout << endl;
}

```

```Output
The operand valarray va is:
( 0 2 2 2 2 2 2 2 2 2 )
The new valarray initialized from the slice is vaSlice =
va[slice( 2, 4, 3)] = ( 0 0 0 )
1 2 3 4
```

## <a name="value_type"></a>  valarray::value_type

valarray に格納された要素の型を表す型。

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `Type` のシノニムです。

### <a name="example"></a>例

```cpp
// valarray_value_type.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    valarray<int> va ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        va [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        va [ i ] =  -1;

    cout << "The initial operand valarray is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;

    // value_type declaration and initialization:
    valarray<int>::value_type Right = 10;

    cout << "The decalared value_type Right is: "
            << Right << endl;
    va *= Right;
    cout << "The resulting valarray is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;
}
/* Output:
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).
The decalared value_type Right is: 10
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).
*/
```

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
