---
title: raw_storage_iterator クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
ms.openlocfilehash: 062a3db5c28bc463d6346a26cf1385adecd41183
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217637"
---
# <a name="raw_storage_iterator-class"></a>raw_storage_iterator クラス

アルゴリズムの結果を初期化されていないメモリに格納するために用意されたアダプター クラスです。

## <a name="syntax"></a>構文

```cpp
template <class OutputIterator, class Type>
    class raw_storage_iterator
```

### <a name="parameters"></a>パラメーター

*OutputIterator*\
格納されるオブジェクトの出力反復子を指定します。

*各種*\
ストレージが割り当てられるオブジェクトの型。

## <a name="remarks"></a>解説

クラスは、生成されたシーケンス内の型のオブジェクトを構築する出力反復子を表し `Type` ます。 クラスのオブジェクトは、 `raw_storage_iterator` \< **ForwardIterator**, **Type**> `ForwardIterator` オブジェクトの構築時に指定したクラスの前方反復子オブジェクトを介してストレージにアクセスします。 クラスの最初のオブジェクトの場合 `ForwardIterator` 、式は、生成されたシーケンスの次のオブジェクト (型の) に対して、構築されていないストレージを** & \* 最初**に指定する必要があり `Type` ます。

このアダプター クラスは、メモリの割り当てとオブジェクトの構築を分離する必要がある場合に使用されます。 `raw_storage_iterator` は、`malloc` 関数を使用して割り当てられたメモリなど、初期化されていないストレージにオブジェクトをコピーするために使用できます。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|||
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|指定した基になる出力反復子を使用して、生のストレージの反復子を構築します。|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[element_type](#element_type)|生のストレージ反復子によって格納される要素を記述する型を提供します。|
|[iter_type](#iter_type)|生のストレージ反復子の基になる反復子を記述する型を提供します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator](#op_star)|出力反復子式を実装するために使用される逆参照演算子 \* `ii`  =  `x` 。|
|[operator =](#op_eq)|\* `i`  =  `x` メモリに格納するための生のストレージ反復子式を実装するために使用される代入演算子。|
|[+ + 演算子](#op_add_add)|生のストレージ反復子の前置インクリメント演算子と後置インクリメント演算子。|

### <a name="element_type"></a><a name="element_type"></a>element_type

生のストレージ反復子によって格納される要素を記述する型を提供します。

```cpp
typedef Type element_type;
```

#### <a name="remarks"></a>解説

この型は、raw_storage_iterator クラステンプレートパラメーターのシノニムです `Type` 。

### <a name="iter_type"></a><a name="iter_type"></a>iter_type

生のストレージ反復子の基になる反復子を記述する型を提供します。

```cpp
typedef ForwardIterator iter_type;
```

#### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `ForwardIterator` のシノニムです。

### <a name="operator"></a><a name="op_star"></a>operator\*

生のストレージ反復子式 \* *ii*  =  *x*を実装するために使用される逆参照演算子。

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

#### <a name="return-value"></a>戻り値

生のストレージ反復子への参照

#### <a name="remarks"></a>解説

の要件として、 `ForwardIterator` 生のストレージ反復子は、式 \* *ii*  =  *t*が有効であること、 **`operator`** または自体については何も必要としないという条件を満たしている必要があり `operator=` ます。 この実装のメンバー演算子は** \* this**を返します。したがって、 [operator =](#op_eq)(**型**&) は、ptr などの式で実際のストアを実行でき \* *ptr*  =  `val` ます。

#### <a name="example"></a>例

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
*pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_eq"></a>operator =

\* *i*  =  メモリに格納するための生のストレージ反復子式 i*x*を実装するために使用される代入演算子。

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

#### <a name="parameters"></a>パラメーター

*val*\
`Type`メモリに挿入される型のオブジェクトの値。

#### <a name="return-value"></a>戻り値

この演算子は、メモリに `val` を挿入し、生のストレージ反復子への参照を返します。

#### <a name="remarks"></a>解説

生のストレージ反復子が満たす必要のある状態の要件では、 `ForwardIterator` 式 ii t だけが有効であること、 \* *ii*  =  *t*または自体については何もないということを前提として **`operator`** `operator=` います。 これらのメンバー演算子は **`*this`** を返します。

代入演算子は、 `first` 配置の新しい式を評価することによって、格納された反復子の値を使用して、出力シーケンス内の次のオブジェクトを構築し `new ( (void*) & *first ) Type( val )` ます。

#### <a name="example"></a>例

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_add_add"></a>+ + 演算子

生のストレージ反復子の前置インクリメント演算子と後置インクリメント演算子。

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

#### <a name="return-value"></a>戻り値

生のストレージ反復子または生のストレージ反復子への参照。

#### <a name="remarks"></a>解説

最初の演算子は、最終的に、 `CharType` 関連付けられている入力ストリームから型のオブジェクトの抽出と格納を試みます。 2 つ目の演算子は、オブジェクトのコピーを作成して、オブジェクトをインクリメントしてから、そのコピーを返します。

最初の前置インクリメント演算子は、格納されている出力反復子オブジェクトをインクリメントしてから、 ** \* この**を返します。

2番目の後置インクリメント演算子は、 ** \* この**のコピーを作成し、格納されている出力反復子オブジェクトをインクリメントしてから、そのコピーを返します。

コンストラクターは、 `first` 出力反復子オブジェクトとしてを格納します。

#### <a name="example"></a>例

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
      *it = 2 * i;
   };

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
```

```Output
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
```

### <a name="raw_storage_iterator"></a><a name="raw_storage_iterator"></a>raw_storage_iterator

指定した基になる出力反復子を使用して、生のストレージの反復子を構築します。

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

#### <a name="parameters"></a>パラメーター

*まずは*\
構築されている `raw_storage_iterator` オブジェクトを基にすることになる前方反復子。

#### <a name="example"></a>例

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
```

```Output
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
```
