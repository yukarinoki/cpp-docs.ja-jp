---
title: gslice クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice
- valarray/std::gslice::size
- valarray/std::gslice::start
- valarray/std::gslice::stride
helpviewer_keywords:
- std::gslice [C++]
- std::gslice [C++], size
- std::gslice [C++], start
- std::gslice [C++], stride
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
ms.openlocfilehash: 07c987fb08a213bb66da628bec3021a3bf9ba24a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370634"
---
# <a name="gslice-class"></a>gslice クラス

valarray の多次元のサブセットを定義するのに使用する、値を配列するための utility クラス。 valarray が配列内のすべての要素を持つ多次元行列と見なされる場合、スライスにより多次元配列からベクターが抽出されます。

## <a name="remarks"></a>解説

このクラスには、[gslice_array](../standard-library/gslice-array-class.md) 型のオブジェクトの特性を示すパラメーターが格納されます。 valarray のサブセットは、クラス gslice のオブジェクトがクラス[valarray](../standard-library/valarray-class.md#op_at)**\<Type>** のオブジェクトの引数として指定されるときに間接的に構築されます。 親の valarray から選択したサブセットを指定する格納値には、以下が含まれています。

- 開始インデックス。

- クラス`valarray<size_t>`の長さベクトル。

- クラス`valarray<size_t>`のストライドベクトル。

これら 2 つのベクターは同じ長さにする必要があります。

gslice によって定義されたセットが定数の valarray のサブセットの場合、gslice は新しい valarray です。 gslice によって定義されたセットが非定数の valarray のサブセットの場合、gslice には元の valarray に対する参照セマンティクスが含まれます。 非定数 valarray の評価メカニズムを使用すると、時間とメモリを節約できます。

valarray での操作は、gslices によって定義されたソースとターゲットのサブセットが同じでなく、すべてのインデックスが有効な場合にのみ保証されます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[gslice](#gslice)|すべて指定された要素で始まる、`valarray` の複数のスライスからなる `valarray` のサブセットを定義します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[サイズ](#size)|`valarray` の一般的なスライスの要素数を指定する配列の値を検索します。|
|[開始](#start)|`valarray` の一般的なスライスの開始インデックスを検索します。|
|[ストライド](#stride)|`valarray` の一般的なスライスの要素間の距離を検索します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="gslicegslice"></a><a name="gslice"></a>gスライス::gスライス

valarray の多次元スライスを定義するのに使用する valarray のユーティリティ クラス。

```cpp
gslice();

gslice(
    size_t _StartIndex,
    const valarray<size_t>& _LenArray,
    const valarray<size_t>& _IncArray);
```

### <a name="parameters"></a>パラメーター

*_StartIndex*\
サブセットの最初の要素の valarray インデックス。

*_LenArray*\
各スライスに要素の数を指定する配列。

*_IncArray*\
各スライスにストライドを指定する配列。

### <a name="return-value"></a>戻り値

既定のコンストラクターは、開始インデックスに対してゼロを格納し、長さおよびストライド ベクターに対して長さゼロのベクターを格納します。 2 番目のコンストラクターは、開始インデックスの *_StartIndex、* 長さの配列の *_LenArray、* ストライド配列の *_IncArray*を格納します。

### <a name="remarks"></a>解説

**gslice** は、すべて指定された要素で始まる valarray の複数のスライスで構成される valarray のサブセットを定義します。 `gslice` と [slice::slice](../standard-library/slice-class.md#slice) の唯一の違いは、複数のスライスを定義する配列を使用する機能です。 最初のスライスには *、_StartIndex*のインデックスを持つ最初の要素 *、_LenArray*の最初の要素で指定された要素の数、および_IncArrayの最初の要素によって与えられたストライド*があります*。 次の一連の直交スライスのセットには、最初のスライスで指定された最初の要素が含まれます。 *_LenArray*の 2 番目の要素は、要素の数を指定します。 ストライドは *、_IncArray*の 2 番目の要素によって与えられます。 スライスの 3 番目のディメンションは開始要素として、2 次元配列の要素を取得し、同様に続行します。

### <a name="example"></a>例

```cpp
// gslice_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:" << endl << "(";
   for ( i = 0 ; i < 20 ; i++ )
      cout << " " << va [ i ];
   cout << " )" << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];

   cout << "The valarray for vaGSlice is vaResult:" << endl
        << "va[vaGSlice] = (";

   for ( i = 0 ; i < 8 ; i++ )
      cout << " " << vaResult [ i ];
   cout << ")" << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 )
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19)
```

## <a name="gslicesize"></a><a name="size"></a>gスライス::サイズ

valarray の一般的なスライスの要素数を指定する配列の値を検索します。

```cpp
valarray<size_t> size() const;
```

### <a name="return-value"></a>戻り値

valarray の一般的なスライスの各スライス内の要素数を指定する valarray。

### <a name="remarks"></a>解説

このメンバー関数は、格納されているスライスの長さを返します。

### <a name="example"></a>例

```cpp
// gslice_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t sizeVA;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sizeVA = va.size ( );
   cout << "The size of the valarray is: "
        << sizeVA << "." << endl << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> sizeGS = vaGSlice.size ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The size of vaResult is:"
        << "\n vaGSlice.size ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << sizeGS[ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The size of the valarray is: 20.

The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The size of vaResult is:
vaGSlice.size ( ) = ( 4 4 ).
```

## <a name="gslicestart"></a><a name="start"></a>gスライス::開始

valarray の一般的なスライスの開始インデックスを検索します。

```cpp
size_t start() const;
```

### <a name="return-value"></a>戻り値

valarray の一般的なスライスの開始インデックス。

### <a name="example"></a>例

```cpp
// gslice_start.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   size_t vaGSstart = vaGSlice.start ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The index of the first element of vaResult is: "
        << vaGSstart << "." << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The index of the first element of vaResult is: 0.
```

## <a name="gslicestride"></a><a name="stride"></a>グスライス::ストライド

valarray の一般的なスライスの要素間の距離を検索します。

```cpp
valarray<size_t> stride() const;
```

### <a name="return-value"></a>戻り値

valarray の一般的なスライスの各スライス内の要素間の距離を指定する valarray。

### <a name="example"></a>例

```cpp
// gslice_stride.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for (i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> strideGS = vaGSlice.stride ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The strides of vaResult are:"
        << "\n vaGSlice.stride ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << strideGS[ i ] << " ";
   cout << ")." << endl;

}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The strides of vaResult are:
vaGSlice.stride ( ) = ( 7 4 ).
```

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
