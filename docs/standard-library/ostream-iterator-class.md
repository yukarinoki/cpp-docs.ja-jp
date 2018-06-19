---
title: ostream_iterator クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iterator/std::ostream_iterator
- iterator/std::ostream_iterator::char_type
- iterator/std::ostream_iterator::ostream_type
- iterator/std::ostream_iterator::traits_type
dev_langs:
- C++
helpviewer_keywords:
- std::ostream_iterator [C++]
- std::ostream_iterator [C++], char_type
- std::ostream_iterator [C++], ostream_type
- std::ostream_iterator [C++], traits_type
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49626cbb33ed1220ad82cbec10ad675769b054d6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863609"
---
# <a name="ostreamiterator-class"></a>ostream_iterator クラス

テンプレート クラス ostream_iterator は、抽出**演算子 <<** を使用して連続する要素を出力ストリームに書き込む出力反復子オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>パラメーター

*型*出力ストリームに挿入するオブジェクトの型。

`CharType` 文字の種類を表す型、`ostream_iterator`です。 この引数は省略可能であり、既定値は `char` です。

`Traits` 文字の種類を表す型、`ostream_iterator`です。 この引数は省略可能であり、既定値は `char_traits`\< *CharType>* です。

ostream_iterator クラスは出力反復子の要件を満たす必要があります。 アルゴリズムは `ostream_iterator` を使用して出力ストリームに直接書き込むことができます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[ostream_iterator](#ostream_iterator)|出力ストリームに書き込むために初期化され、区切られた `ostream_iterator` を構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|`ostream_iterator` の文字型を提供する型。|
|[ostream_type](#ostream_type)|`ostream_iterator` のストリーム型を提供する型。|
|[traits_type](#traits_type)|`ostream_iterator` の文字特性型を提供する型。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator*](#op_star)|出力反復子式 * `i` = `x` を実装するために使用される逆参照演算子。|
|[operator++](#op_add_add)|操作が呼び出される前に示したものと同じオブジェクトに `ostream_iterator` を返す、実質的な機能を持たないインクリメント演算子。|
|[operator=](#op_eq)|出力ストリームに書き込むための出力反復子式 * `i` = `x` を実装するために使用される代入演算子。|

## <a name="requirements"></a>要件

**ヘッダー:** \<iterator>

**名前空間:** std

## <a name="char_type"></a>  ostream_iterator::char_type

反復子の文字型を提供する型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **CharType** のシノニムです。

### <a name="example"></a>例

```cpp
// ostream_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostream_iterator<int>::char_type CHT1;
   typedef ostream_iterator<int>::traits_type CHTR1;

   // ostream_iterator for stream cout
   // with new line delimiter:
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream:
   cout << "The integers written to the output stream\n"
        << "by intOut are:" << endl;
 *intOut = 10;
 *intOut = 20;
 *intOut = 30;
}
\* Output:
The integers written to the output stream
by intOut are:
10
20
30
*\
```

## <a name="op_star"></a>  ostream_iterator::operator*

出力反復子式 \* *ii* = *x* を実装するために使用される逆参照演算子。

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>戻り値

`ostream_iterator` への参照。

### <a name="remarks"></a>コメント

`ostream_iterator` が満たす必要のある出力反復子の要件は、式 \* *ii* = *t* が有効であることを必要とするのみで、**演算子** または `operator=` 自体については何も必要としないことです。 この実装のメンバー演算子は **\*this** を返します。

### <a name="example"></a>例

```cpp
// ostream_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
 *intOut = 10;
   intOut++;      // No effect on iterator position
 *intOut = 20;
 *intOut = 30;
}
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="op_add_add"></a>  ostream_iterator::operator++

操作が呼び出される前に示したものと同じオブジェクトに `ostream_iterator` を返す、実質的な機能を持たないインクリメント演算子。

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>戻り値

`ostream_iterator` への参照。

### <a name="remarks"></a>コメント

これらのメンバー演算子はいずれも **\*this** を返します。

### <a name="example"></a>例

```cpp
// ostream_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
 *intOut = 10;
   intOut++;      // No effect on iterator position
 *intOut = 20;
 *intOut = 30;
}
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="op_eq"></a>  ostream_iterator::operator=

出力ストリームに書き込むための出力反復子式 * `i` = `x` を実装するために使用される代入演算子。

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>パラメーター

`val` 型のオブジェクトの値`Type`出力ストリームに挿入します。

### <a name="return-value"></a>戻り値

この演算子はオブジェクトに関連付けられた出力ストリームに `val` を挿入してから、[ostream_iterator コンストラクター](#ostream_iterator)で指定された区切り記号を挿入して (存在する場合)、`ostream_iterator` への参照を返します。

### <a name="remarks"></a>コメント

`ostream_iterator` が満たす必要のある出力反復子の要件は、式 * `ii` = `t` が有効であることを必要とするのみで、この演算子または operator= 自体については何も必要としないことです。 このメンバー演算子は、`*this` を返します。

### <a name="example"></a>例

```cpp
// ostream_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
 *intOut = 10;
   intOut++;      // No effect on iterator position
 *intOut = 20;
 *intOut = 30;
}
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="ostream_iterator"></a>  ostream_iterator::ostream_iterator

出力ストリームに書き込むために初期化され、区切られた `ostream_iterator` を構築します。

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>パラメーター

`_Ostr` 型の出力ストリーム[ostream_iterator::ostream_type](#ostream_type)を反復処理します。

`_Delimiter` 値の間の出力ストリームに挿入される区切り記号です。

### <a name="remarks"></a>コメント

最初のコンストラクターは、出力ストリーム ポインターを `&_Ostr` で初期化します。 区切り記号文字列ポインターは、空の文字列を指定します。

2 番目のコンス トラクターは、出力ストリーム ポインターを `&_Ostr` で初期化し、区切り記号文字列ポインターを `_Delimiter` で初期化します。

### <a name="example"></a>例

```cpp
// ostream_iterator_ostream_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   ostream_iterator<int> intOut ( cout , "\n" );
 *intOut = 10;
   intOut++;
 *intOut = 20;
   intOut++;

   int i;
   vector<int> vec;
   for ( i = 1 ; i < 7 ; ++i )
   {
      vec.push_back (  i );
   }

   // Write elements to standard output stream
   cout << "Elements output without delimiter: ";
   copy ( vec.begin ( ), vec.end ( ),
          ostream_iterator<int> ( cout ) );
   cout << endl;

   // Write elements with delimiter " : " to output stream
   cout << "Elements output with delimiter: ";
   copy ( vec.begin ( ), vec.end ( ),
          ostream_iterator<int> ( cout, " : " ) );
   cout << endl;
}
\* Output:
10
20
Elements output without delimiter: 123456
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :
*\
```

## <a name="ostream_type"></a>  ostream_iterator::ostream_type

反復子のストリーム型を提供する型。

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>コメント

この型は、書き込みに使用できるオブジェクトを定義する iostream 階層のストリーム クラスである [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`> のシノニムです。

### <a name="example"></a>例

`ostream_type` を宣言して使用する方法の例については、[ostream_iterator](#ostream_iterator) に関するセクションをご覧ください。

## <a name="traits_type"></a>  ostream_iterator::traits_type

反復子の文字特性型を提供する型。

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **Traits** のシノニムです。

### <a name="example"></a>例

```cpp
// ostream_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // The following not OK, but are just the default values:
   typedef ostream_iterator<int>::char_type CHT1;
   typedef ostream_iterator<int>::traits_type CHTR1;

   // ostream_iterator for stream cout
   // with new line delimiter:
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream:
   cout << "The integers written to output stream\n"
        << "by intOut are:" << endl;
 *intOut = 1;
 *intOut = 10;
 *intOut = 100;
}
\* Output:
The integers written to output stream
by intOut are:
1
10
100
*\
```

## <a name="see-also"></a>関連項目

[\<iterator>](../standard-library/iterator.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
