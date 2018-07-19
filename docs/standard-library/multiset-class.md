---
title: multiset クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- set/std::multiset
- set/std::multiset::allocator_type
- set/std::multiset::const_iterator
- set/std::multiset::const_pointer
- set/std::multiset::const_reference
- set/std::multiset::const_reverse_iterator
- set/std::multiset::difference_type
- set/std::multiset::iterator
- set/std::multiset::key_compare
- set/std::multiset::key_type
- set/std::multiset::pointer
- set/std::multiset::reference
- set/std::multiset::reverse_iterator
- set/std::multiset::size_type
- set/std::multiset::value_compare
- set/std::multiset::value_type
- set/std::multiset::begin
- set/std::multiset::cbegin
- set/std::multiset::cend
- set/std::multiset::clear
- set/std::multiset::count
- set/std::multiset::crbegin
- set/std::multiset::crend
- set/std::multiset::emplace
- set/std::multiset::emplace_hint
- set/std::multiset::empty
- set/std::multiset::end
- set/std::multiset::equal_range
- set/std::multiset::erase
- set/std::multiset::find
- set/std::multiset::get_allocator
- set/std::multiset::insert
- set/std::multiset::key_comp
- set/std::multiset::lower_bound
- set/std::multiset::max_size
- set/std::multiset::rbegin
- set/std::multiset::rend
- set/std::multiset::size
- set/std::multiset::swap
- set/std::multiset::upper_bound
- set/std::multiset::value_comp
dev_langs:
- C++
helpviewer_keywords:
- std::multiset [C++]
- std::multiset [C++], allocator_type
- std::multiset [C++], const_iterator
- std::multiset [C++], const_pointer
- std::multiset [C++], const_reference
- std::multiset [C++], const_reverse_iterator
- std::multiset [C++], difference_type
- std::multiset [C++], iterator
- std::multiset [C++], key_compare
- std::multiset [C++], key_type
- std::multiset [C++], pointer
- std::multiset [C++], reference
- std::multiset [C++], reverse_iterator
- std::multiset [C++], size_type
- std::multiset [C++], value_compare
- std::multiset [C++], value_type
- std::multiset [C++], begin
- std::multiset [C++], cbegin
- std::multiset [C++], cend
- std::multiset [C++], clear
- std::multiset [C++], count
- std::multiset [C++], crbegin
- std::multiset [C++], crend
- std::multiset [C++], emplace
- std::multiset [C++], emplace_hint
- std::multiset [C++], empty
- std::multiset [C++], end
- std::multiset [C++], equal_range
- std::multiset [C++], erase
- std::multiset [C++], find
- std::multiset [C++], get_allocator
- std::multiset [C++], insert
- std::multiset [C++], key_comp
- std::multiset [C++], lower_bound
- std::multiset [C++], max_size
- std::multiset [C++], rbegin
- std::multiset [C++], rend
- std::multiset [C++], size
- std::multiset [C++], swap
- std::multiset [C++], upper_bound
- std::multiset [C++], value_comp
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07e38d11ef25ebc2f1da888594ab84fe2261c53a
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028334"
---
# <a name="multiset-class"></a>multiset クラス

C++ 標準ライブラリの multiset クラスは、コレクションのデータを格納および取得するために使用されます。コレクションに含まれる要素の値は一意である必要はなく、データを自動的に順序付けるキー値として使用されます。 multiset 内の要素のキー値は直接変更できません。 代わりに、以前の値を削除し、新しい値の要素を挿入する必要があります。

## <a name="syntax"></a>構文

```cpp
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>
class multiset
```

### <a name="parameters"></a>パラメーター

*キー* multiset に格納される要素のデータを入力します。

*比較*multiset 内の相対順序を決定する並べ替えキーとして 2 つの要素の値を比較できる関数オブジェクトを提供する型。 二項述語 **less**\<Key> が既定値です。

C++ 14 では、型パラメーターを使用せずに `std::less<>` 述語または `std::greater<>` 述語を指定することで、異種ルックアップを有効にすることができます。 詳細については、「[連想コンテナーの異種ルックアップ](../standard-library/stl-containers.md#sequence_containers)」をご覧ください。

*アロケーター* multiset の割り当てとメモリの解放に関する詳細をカプセル化する格納されたアロケーター オブジェクトを表す型です。 既定値は **アロケーター * * *\<キー >。*

## <a name="remarks"></a>Remarks

C++ 標準ライブラリ multiset クラスには下記の特徴があります。

- 連想コンテナーであり、関連付けられたキー値に基づいて要素の値を効率的に取得できるようにする可変サイズのコンテナーとして機能します。

- 反転することができます。これは、要素にアクセスするための双方向反復子が用意されているためです。

- 並べ替えが実行されます。これは、指定した比較関数に従ってコンテナー内のキー値によって要素に順序が設定されるためです。

- 複数対応です。要素は一意のキーを持つ必要がないので、関連する多くの要素値を 1 つのキー値が持つことができるためです。

- 単純な連想コンテナーです。これは、要素値がキー値であるためです。

- テンプレート クラスとして機能します。これは、このクラスに用意されている機能が汎用的な機能であり、要素として保持されているデータの特定の型に依存しないためです。 使用されているデータ型は、クラス テンプレートで比較関数やアロケーターと共にパラメーターとして指定されます。

multiset クラスに用意されている反復子は双方向反復子ですが、クラス メンバー関数 [insert](#insert) と [multiset](#multiset) には、弱い入力反復子をテンプレート パラメーターとしてとるバージョンがあります。この反復子の機能要件は、双方向反復子のクラスで保証されている要件よりも低くなっています。 これらの反復子の機能に差異があるのは、反復子の概念が異なっているためです。 反復子の各概念には、反復子独自の一連の要件が含まれています。また、それらの要件を使用するアルゴリズムでは、反復子の種類ごとに指定されている要件に対して、前提を絞り込む必要があります。 たとえば、一部のオブジェクトを参照するために入力反復子が逆参照される可能性があることを前提とする場合があります。さらに、シーケンス内にある次の反復子に対して逆参照が増加する可能性があることを前提とする場合もあります。 これは最小限の機能ですが、クラスのメンバー関数という文脈で反復子の範囲 [ `First`, `Last`) について意味を成していれば十分です。

一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。 連想コンテナーは、検索、挿入、削除の各操作用に最適化されています。 これらの操作を明示的にサポートするメンバー関数は効率的であり、処理時間は平均的にコンテナー内にある要素の数の対数に比例します。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を具体的に指す反復子だけが無効化されます。

値とキーを関連付ける条件をアプリケーションが満たしている場合、multiset は最適な連想コンテナーとなっている必要があります。 multiset の要素は複数の場合があり、それ自体の並べ替えキーとして機能する場合があるため、キーは一意ではありません。 この種類の構造体のモデルは、単語が複数回出現する可能性がある単語の順序付きのリストです。 単語が複数回出現することが許可されてない場合は、set が適切なコンテナー構造体となります。 一意の定義が値として一意のキーワードのリストにアタッチされている場合は、map がこのデータを格納するのに適切な構造体です。 定義が一意でない場合は、multimap が最適なコンテナーです。

Multiset が型の格納されている関数オブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます*比較*します。 この格納されているオブジェクトは比較関数であり、メンバー関数 [key_comp](#key_comp) を呼び出すことによってアクセスできます。 通常、要素は、この順序を確立するために小なり比較だけを実行できる必要があります。これにより、2 つの要素が指定されたときに、それらの要素が等しいか (どちらか一方が小さくはない)、または一方が他方より小さいかを判断できます。 この結果、等価でない複数の要素間で順序が付けられます。 テクニカル ノートでは、比較関数は、数学上の標準的な意味で厳密弱順序を発生させる二項述語であると示されています。 二項述語 *f*( *x*, *y*) は、2 つの引数オブジェクト *x* および *y* と戻り値 (**true** または **false**) を持つ関数オブジェクトです。 set に適用される順序付けは、二項述語が非再帰、反対称、推移的であり、等価性が推移的である (2 つのオブジェクト x と y が、*f*( *x,y*) と *f*( *y,x*) の両方が false の場合に等価になるように定義されている) 場合、厳密弱順序になります。 2 つのキーの等値に関する条件が等価性の条件よりも厳しく、優先される場合、順序付けは完全な順序付け (すべての要素が相互の値に基づいて並べ替えられる) となり、一致するそれぞれのキーを識別するのが難しくなります。

C++ 14 では、型パラメーターを使用せずに `std::less<>` 述語または `std::greater<>` 述語を指定することで、異種ルックアップを有効にすることができます。 詳細については、「[連想コンテナーの異種ルックアップ](../standard-library/stl-containers.md#sequence_containers)」をご覧ください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[multiset](#multiset)|空であるか、指定された `multiset` の全体または一部のコピーである `multiset` を構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[allocator_type](#allocator_type)|`allocator` オブジェクトの `multiset` クラスの typedef。|
|[const_iterator](#const_iterator)|読み取ることができる双方向反復子の typedef、 **const**内の要素、`multiset`します。|
|[const_pointer](#const_pointer)|ポインターの typedef、 **const**内の要素を`multiset`します。|
|[const_reference](#const_reference)|参照の typedef、 **const**に要素が格納されている、`multiset`読み取りと実行の**const**操作。|
|[const_reverse_iterator](#const_reverse_iterator)|いずれかを読み取ることができる双方向反復子の typedef **const**内の要素、`multiset`します。|
|[difference_type](#difference_type)|反復子が指す要素の範囲内にある `multiset` の要素の数に対する符号付き整数の typedef。|
|[Iterator](#iterator)|`multiset` 内の任意の要素の読み取りまたは変更ができる双方向反復子の typedef。|
|[key_compare](#key_compare)|2 つのキーを比較して、`multiset` 内の 2 つの要素の相対順序を決定できる関数オブジェクトの typedef。|
|[key_type](#key_type)|2 つの並べ替えキーを比較して、`multiset` 内の 2 つの要素の相対順序を決定できる関数オブジェクトの typedef。|
|[pointer](#pointer)|`multiset` 内の要素へのポインターの typedef。|
|[reference](#reference)|`multiset` に格納されている要素への参照の typedef。|
|[reverse_iterator](#reverse_iterator)|反転された `multiset` 内の 1 つの要素の読み取りまたは変更ができる双方向反復子の typedef。|
|[size_type](#size_type)|`multiset` 内の要素の数を表すことができる符号なし整数型。|
|[value_compare](#value_compare)|2 つ要素を並べ替えキーとして比較して、`multiset` 内の相対順序を決定できる関数オブジェクトの typedef。|
|[value_type](#value_type)|要素としての値として、容量が `multiset` として格納されるオブジェクトを表す typedef。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[begin](#begin)|`multiset` 内の最初の要素を指す反復子を返します。|
|[cbegin](#cbegin)|`multiset` 内の最初の要素を指す定数反復子を返します。|
|[cend](#cend)|`multiset` 内の最後の要素の次の位置を指す定数反復子を返します。|
|[clear](#clear)|`multiset` のすべての要素を消去します。|
|[count](#count)|パラメーターに指定したキーに一致するキーを持つ、`multiset` 内の要素の数を返します。|
|[crbegin](#crbegin)|反転された set 内の最初の要素を指す定数反復子を返します。|
|[crend](#crend)|反転された set 内の最後の要素の次の位置を指す定数反復子を返します。|
|[emplace](#emplace)|インプレースで構築された要素を `multiset` に挿入します。|
|[emplace_hint](#emplace_hint)|インプレースで構築された要素を、配置ヒントと共に `multiset` に挿入します。|
|[empty](#empty)|`multiset` が空かどうかをテストします。|
|[end](#end)|`multiset` 内の最後の要素の次の位置を指す反復子を返します。|
|[equal_range](#equal_range)|反復子のペアを返します。 ペアに含まれる最初の反復子は、指定したキーよりも大きいキーを持つ、`multiset` 内の最初の要素を指します。 ペアに含まれる 2 番目の反復子は、指定したキー以上のキーを持つ、`multiset` 内の最初の要素を指します。|
|[erase](#erase)|`multiset` 内の要素または要素の範囲を指定した位置から削除するか、または指定したキーと一致する要素を削除します。|
|[find](#find)|指定したキーと同じキーを持つ、`multiset` 内の要素の位置を指す反復子を返します。|
|[get_allocator](#get_allocator)|`allocator` の構築に使用される `multiset` オブジェクトのコピーを返します。|
|[insert](#insert)|`multiset` に要素または要素範囲を挿入します。|
|[key_comp](#key_comp)|2 つの並べ替えキーを比較して、`multiset` 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供します。|
|[lower_bound](#lower_bound)|指定したキー以上のキーを持つ、`multiset` 内の最初の要素を指す反復子を返します。|
|[max_size](#max_size)|`multiset` の最大長を返します。|
|[rbegin](#rbegin)|反転された `multiset` 内の最初の要素を指す反復子を返します。|
|[rend](#rend)|反転された `multiset` 内の最後の要素の次の位置を指す反復子を返します。|
|[size](#size)|`multiset` 内の要素数を返します。|
|[swap](#swap)|2 つの `multiset` の要素を交換します。|
|[upper_bound](#upper_bound)|指定したキー以上のキーを持つ、`multiset` 内の最初の要素を指す反復子を返します。|
|[value_comp](#value_comp)|`multiset` 内の要素の値を並べ替えるために使用される比較オブジェクトのコピーを取得します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_eq)|別の `multiset` のコピーで `multiset` の要素を置き換えます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<set>

**名前空間:** std

## <a name="allocator_type"></a>  multiset::allocator_type

multiset オブジェクトのアロケーター クラスを表す型。

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Remarks

`allocator_type` はテンプレート パラメーター `Allocator` のシノニムです。

`Allocator` の詳細については、[multiset クラス](../standard-library/multiset-class.md)のトピックのコメントのセクションをご覧ください。

### <a name="example"></a>例

`allocator_type` の使用例については、[get_allocator](#get_allocator) の例をご覧ください。

## <a name="begin"></a>  multiset::begin

multiset の 1 つ目の要素を指す反復子を返します。

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>戻り値

multiset 内の最初の要素、または空の multiset の次の位置を指す、双方向反復子。

### <a name="example"></a>例

```cpp
// multiset_begin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::const_iterator ms1_cIter;

   ms1.insert( 1 );
   ms1.insert( 2 );
   ms1.insert( 3 );

   ms1_Iter = ms1.begin( );
   cout << "The first element of ms1 is " << *ms1_Iter << endl;

   ms1_Iter = ms1.begin( );
   ms1.erase( ms1_Iter );

   // The following 2 lines would err as the iterator is const
   // ms1_cIter = ms1.begin( );
   // ms1.erase( ms1_cIter );

   ms1_cIter = ms1.begin( );
   cout << "The first element of ms1 is now " << *ms1_cIter << endl;
}
```

```Output
The first element of ms1 is 1
The first element of ms1 is now 2
```

## <a name="cbegin"></a>  multiset::cbegin

返します、 **const**範囲の最初の要素を指す反復子。

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>戻り値

A **const**最初の要素の範囲、または空の範囲の末尾の次の場所を指す双方向アクセス反復子 (空の範囲、 `cbegin() == cend()`)。

### <a name="remarks"></a>Remarks

`cbegin` の戻り値で範囲内の要素を変更することはできません。

`begin()` メンバー関数の代わりにこのメンバー関数を使用して、戻り値が `const_iterator` になることを保証できます。 通常は、次の例に示すように [auto](../cpp/auto-cpp.md) 型推論キーワードと共に使用します。 例では、検討してください。`Container`に変更可能な (非**const**) をサポートする任意の種類のコンテナー`begin()`と`cbegin()`します。

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  multiset::cend

返します、 **const**範囲の最後の要素の次の位置を指す反復子。

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>戻り値

A **const**範囲の終了位置を指す双方向アクセス反復子。

### <a name="remarks"></a>Remarks

`cend` は、反復子が範囲の末尾を超えたかどうかをテストするために使用されます。

`end()` メンバー関数の代わりにこのメンバー関数を使用して、戻り値が `const_iterator` になることを保証できます。 通常は、次の例に示すように [auto](../cpp/auto-cpp.md) 型推論キーワードと共に使用します。 例では、検討してください。`Container`に変更可能な (非**const**) をサポートする任意の種類のコンテナー`end()`と`cend()`します。

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

`cend` によって返された値は逆参照しないでください。

## <a name="clear"></a>  multiset::clear

multiset のすべての要素を消去します。

```cpp
void clear();
```

### <a name="example"></a>例

```cpp
// multiset_clear.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 1 );
   ms1.insert( 2 );

   cout << "The size of the multiset is initially "
        << ms1.size( ) << "." << endl;

   ms1.clear( );
   cout << "The size of the multiset after clearing is "
        << ms1.size( ) << "." << endl;
}
```

```Output
The size of the multiset is initially 2.
The size of the multiset after clearing is 0.
```

## <a name="const_iterator"></a>  multiset::const_iterator

multiset 内の **const** 要素を読み取ることができる双方向反復子を提供する型。

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Remarks

`const_iterator` 型で要素の値を変更することはできません。

### <a name="example"></a>例

`const_iterator` の使用例については、[begin](#begin) の例をご覧ください。

## <a name="const_pointer"></a>  multiset::const_pointer

multiset 内の **const** 要素へのポインターを提供する型。

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Remarks

`const_pointer` 型で要素の値を変更することはできません。

ほとんどの場合、multiset オブジェクト内の要素にアクセスするには、[反復子](#iterator) を使用する必要があります。

## <a name="const_reference"></a>  multiset::const_reference

読み取りと **const** 操作の実行のために、multiset に格納された **const** 要素への参照を提供する型。

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="example"></a>例

```cpp
// multiset_const_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a const_reference &Ref1
   // to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;

   // The following line would cause an error because the
   // const_reference cannot be used to modify the multiset
   // Ref1 = Ref1 + 5;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="const_reverse_iterator"></a>  multiset::const_reverse_iterator

multiset 内の任意の **const** 要素を読み取ることができる双方向反復子を提供する型。

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Remarks

`const_reverse_iterator` 型は要素の値を変更できず、逆の順序で multiset を反復処理するために使用します。

### <a name="example"></a>例

`const_reverse_iterator` の宣言方法や使用方法の例については、[rend](#rend) の例をご覧ください。

## <a name="count"></a>  multiset::count

パラメーター指定したキーと一致するキーを持つ、multiset 内の要素の数を返します。

```cpp
size_type count(const Key& key) const;
```

### <a name="parameters"></a>パラメーター

*キー*照合される multiset の要素のキー。

### <a name="return-value"></a>戻り値

並べ替えキーがパラメーター キーと一致する multiset 内の要素の数。

### <a name="remarks"></a>Remarks

メンバー関数は、次の範囲内の要素 *x* の数を返します。

[ `lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ) ).

### <a name="example"></a>例

multiset::count メンバー関数の使用例を次に示します。

```cpp
// multiset_count.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    multiset<int> ms1;
    multiset<int>::size_type i;

    ms1.insert(1);
    ms1.insert(1);
    ms1.insert(2);

    // Elements do not need to be unique in multiset,
    // so duplicates are allowed and counted.
    i = ms1.count(1);
    cout << "The number of elements in ms1 with a sort key of 1 is: "
         << i << "." << endl;

    i = ms1.count(2);
    cout << "The number of elements in ms1 with a sort key of 2 is: "
         << i << "." << endl;

    i = ms1.count(3);
    cout << "The number of elements in ms1 with a sort key of 3 is: "
         << i << "." << endl;
}
```

```Output
The number of elements in ms1 with a sort key of 1 is: 2.
The number of elements in ms1 with a sort key of 2 is: 1.
The number of elements in ms1 with a sort key of 3 is: 0.
```

## <a name="crbegin"></a>  multiset::crbegin

反転された multiset 内の最初の要素を示す定数反復子を返します。

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>戻り値

反転された multiset 内の最初の要素を示す、または反転されていない multiset 内の最後の要素だったものを示す const 反転双方向反復子。

### <a name="remarks"></a>Remarks

`crbegin` は、begin が multiset で使用されるのと同様に、反転された multiset で使用されます。

`crbegin` の戻り値で multiset オブジェクトを変更することはできません。

`crbegin` を使用して、multiset 内を後方に向かって反復処理できます。

### <a name="example"></a>例

```cpp
// multiset_crbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

```Output
The first element in the reversed multiset is 30.
```

## <a name="crend"></a>  multiset::crend

反転された multiset 内の最後の要素の次の位置を指す定数反復子を返します。

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>戻り値

反転された multiset 内の最後の要素の次の場所 (反転されていない multiset 内の最初の要素の前の場所) を指す定数逆順双方向反復子。

### <a name="remarks"></a>Remarks

`crend` は、[end](#end) が multiset で使用されるのと同様に、反転された multiset で使用されます。

`crend` の戻り値で multiset オブジェクトを変更することはできません。

`crend` を使用して、逆順反復子が multiset の末尾に達したかどうかをテストできます。

`crend` によって返された値は逆参照しないでください。

### <a name="example"></a>例

```cpp
// multiset_crend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_crIter = ms1.crend( ) ;
   ms1_crIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_crIter << "." << endl;
}
```

## <a name="difference_type"></a>  multiset::difference_type

反復子が指す要素の範囲内にある multiset の要素の数を表すのに使用できる符号付き整数型。

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Remarks

`difference_type` は、コンテナーの反復子を減算またはインクリメントするときに返される型です。 通常、`difference_type` は、[ `first`, `last`) の範囲内で、反復子 `first` と `last` の間にある要素の数を表すために使用され、`first` が指す要素と、`last` が指す要素の 1 つ前までの範囲の要素を含みます。

`difference_type` は、入力反復子の要件を満たすすべての反復子 (set などの反転可能なコンテナーによってサポートされる双方向反復子のクラスを含む) に対して使用できますが、反復子間の減算は、vector などのランダム アクセス コンテナーによって提供される、ランダム アクセス反復子によってのみサポートされます。

### <a name="example"></a>例

```cpp
// multiset_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <set>
#include <algorithm>

int main( )
{
   using namespace std;

   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter, ms1_bIter, ms1_eIter;

   ms1.insert( 20 );
   ms1.insert( 10 );
   ms1.insert( 20 );

   ms1_bIter = ms1.begin( );
   ms1_eIter = ms1.end( );

   multiset <int>::difference_type   df_typ5, df_typ10, df_typ20;

   df_typ5 = count( ms1_bIter, ms1_eIter, 5 );
   df_typ10 = count( ms1_bIter, ms1_eIter, 10 );
   df_typ20 = count( ms1_bIter, ms1_eIter, 20 );

   // The keys, and hence the elements, of a multiset are not unique
   cout << "The number '5' occurs " << df_typ5
        << " times in multiset ms1.\n";
   cout << "The number '10' occurs " << df_typ10
        << " times in multiset ms1.\n";
   cout << "The number '20' occurs " << df_typ20
        << " times in multiset ms1.\n";

   // Count the number of elements in a multiset
   multiset <int>::difference_type  df_count = 0;
   ms1_Iter = ms1.begin( );
   while ( ms1_Iter != ms1_eIter)
   {
      df_count++;
      ms1_Iter++;
   }

   cout << "The number of elements in the multiset ms1 is: "
        << df_count << "." << endl;
}
```

```Output
The number '5' occurs 0 times in multiset ms1.
The number '10' occurs 1 times in multiset ms1.
The number '20' occurs 2 times in multiset ms1.
The number of elements in the multiset ms1 is: 3.
```

## <a name="emplace"></a>  multiset::emplace

インプレースで構築された (コピーまたは移動操作が実行されない) 要素を、配置ヒントと一緒に挿入します。

```cpp
template <class... Args>
iterator emplace(Args&&... args);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*引数*|multiset に挿入される要素を構築するために転送される引数。|

### <a name="return-value"></a>戻り値

新しく挿入される要素を指す反復子。

### <a name="remarks"></a>Remarks

この関数では、コンテナー要素を指す参照は無効になりません。ただし、コンテナーを指すすべての反復子が無効になる場合があります。

配置の実行中、例外がスローされるとコンテナーの状態は変更されません。

### <a name="example"></a>例

```cpp
// multiset_emplace.cpp
// compile with: /EHsc
#include <set>
#include <string>
#include <iostream>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{
    multiset<string> s1;

    s1.emplace("Anna");
    s1.emplace("Bob");
    s1.emplace("Carmine");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;

    s1.emplace("Bob");

    cout << "multiset modified, now contains ";
    print(s1);
    cout << endl;
}

```

## <a name="emplace_hint"></a>  multiset::emplace_hint

インプレースで構築された (コピーまたは移動操作が実行されない) 要素を、配置ヒントと一緒に挿入します。

```cpp
template <class... Args>
iterator emplace_hint(
    const_iterator where,
    Args&&... args);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*引数*|multiset に挿入される要素を構築するために転送される引数。|
|*where*|正しい挿入ポイントの検索を開始する場所  (そのポイントの直前に場合*場所*、対数時間ではなく償却定数時間で実行できます)。|

### <a name="return-value"></a>戻り値

新しく挿入される要素を指す反復子。

### <a name="remarks"></a>Remarks

この関数では、コンテナー要素を指す参照は無効になりません。ただし、コンテナーを指すすべての反復子が無効になる場合があります。

配置の実行中、例外がスローされるとコンテナーの状態は変更されません。

コード例については、「[set::emplace_hint](../standard-library/set-class.md#emplace_hint)」をご覧ください。

## <a name="empty"></a>  multiset::empty

multiset が空かどうかをテストします。

```cpp
bool empty() const;
```

### <a name="return-value"></a>戻り値

multiset が空の場合は **true**、multiset が空ではない場合は **false**。

### <a name="example"></a>例

```cpp
// multiset_empty.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2;
   ms1.insert ( 1 );

   if ( ms1.empty( ) )
      cout << "The multiset ms1 is empty." << endl;
   else
      cout << "The multiset ms1 is not empty." << endl;

   if ( ms2.empty( ) )
      cout << "The multiset ms2 is empty." << endl;
   else
      cout << "The multiset ms2 is not empty." << endl;
}
```

```Output
The multiset ms1 is not empty.
The multiset ms2 is empty.
```

## <a name="end"></a>  multiset::end

末尾超え反復子を返します。

```cpp
const_iterator end() const;


iterator end();
```

### <a name="return-value"></a>戻り値

末尾超え反復子。 multiset が空の場合は、`multiset::end() == multiset::begin()`。

### <a name="remarks"></a>Remarks

**end** は、反復子が multiset の末尾を超えたかどうかをテストするために使用します。

**end** によって返された値は逆参照しないでください。

コード例については、「[multiset::find](#find)」をご覧ください。

## <a name="equal_range"></a>  multiset::equal_range

指定したキーよりも大きいキーを持つ multiset 内の最初の要素を指す反復子と、そのキー以上のキーを持つ multiset 内の最初の要素を指す反復子、のペアを返します。

```cpp
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```

### <a name="parameters"></a>パラメーター

*キー*検索対象の multiset の要素の並べ替えキーと比較される引数キー。

### <a name="return-value"></a>戻り値

1 番目がそのキーの [lower_bound](#lower_bound)、2 番目がそのキーの [upper_bound](#upper_bound) である、反復子のペア。

ペアの最初の反復子にアクセスする`pr`を使用して、メンバー関数によって返される、`pr`します。 **最初**、下限の反復子を逆参照するには使用と\*(`pr`します。 **まず**)。 ペアの 2 つ目の反復子にアクセスする`pr`を使用して、メンバー関数によって返される、`pr`します。 **2 番目**、上限の反復子を逆参照するには使用と\*(`pr`します。 **2 つ目**)。

### <a name="example"></a>例

```cpp
// multiset_equal_range.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   typedef multiset<int, less<int> > IntSet;
   IntSet ms1;
   multiset <int> :: const_iterator ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;
   p1 = ms1.equal_range( 20 );

   cout << "The upper bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.second ) << "." << endl;

   cout << "The lower bound of the element with "
        << "a key of 20 in the multiset ms1 is: "
        << *( p1.first ) << "." << endl;

   // Compare the upper_bound called directly
   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "A direct call of upper_bound( 20 ) gives "
        << *ms1_RcIter << "," << endl
        << "matching the 2nd element of the pair"
        << " returned by equal_range( 20 )." << endl;

   p2 = ms1.equal_range( 40 );

   // If no match is found for the key,
   // both elements of the pair return end( )
   if ( ( p2.first == ms1.end( ) ) && ( p2.second == ms1.end( ) ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key less than 40." << endl;
   else
      cout << "The element of multiset ms1 with a key >= 40 is: "
                << *( p1.first ) << "." << endl;
}
```

```Output
The upper bound of the element with a key of 20 in the multiset ms1 is: 30.
The lower bound of the element with a key of 20 in the multiset ms1 is: 20.
A direct call of upper_bound( 20 ) gives 30,
matching the 2nd element of the pair returned by equal_range( 20 ).
The multiset ms1 doesn't have an element with a key less than 40.
```

## <a name="erase"></a>  multiset::erase

multiset 内の要素または要素範囲を指定した位置から削除するか、指定したキーと一致する要素を削除します。

```cpp
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,
    const_iterator Last);

size_type erase(
    const key_type& Key);
```

### <a name="parameters"></a>パラメーター

*場所*を削除する要素の位置。

*最初*を削除する最初の要素の位置。

*最後*を削除する最後の要素の次の位置。

*キー*を削除する要素のキー値。

### <a name="return-value"></a>戻り値

最初の 2 つのメンバー関数では、削除された要素の後にある最初の残存要素を指定する双方向反復子、またはこのような要素が存在しない場合は multiset の最後の要素を指定する双方向反復子が返されます。

3 番目のメンバー関数では、multiset から削除された要素の数が返されます。

### <a name="remarks"></a>Remarks

コード例については、「[set::erase](../standard-library/set-class.md#erase)」をご覧ください。

## <a name="find"></a>  multiset::find

指定したキーと等価のキーを持つ、multiset 内の要素の位置を参照する反復子を返します。

```cpp
iterator find(const Key& key);


const_iterator find(const Key& key) const;
```

### <a name="parameters"></a>パラメーター

*キー*検索対象の multiset の要素の並べ替えキーによって照合されるキーの値。

### <a name="return-value"></a>戻り値

指定したキーを持つ要素の位置を参照する反復子。キーの一致が検出されない場合は、multiset 内の最後の要素の次の位置 (`multiset::end()`)。

### <a name="remarks"></a>Remarks

メンバー関数は、multiset のキーを持つ要素を参照する反復子は、引数を返します。*キー*二項述語に即して小なり比較関係に基づいて順序付けします。

場合の戻り値`find`に割り当てられている、 `const_iterator`、multiset オブジェクトは変更できません。 場合の戻り値`find`に割り当てられている、 `iterator`、multiset オブジェクトを変更できます

### <a name="example"></a>例

```cpp
// compile with: /EHsc /W4 /MTd
#include <set>
#include <iostream>
#include <vector>
#include <string>

using namespace std;

template <typename T> void print_elem(const T& t) {
    cout << "(" << t << ") ";
}

template <typename T> void print_collection(const T& t) {
    cout << t.size() << " elements: ";

    for (const auto& p : t) {
        print_elem(p);
    }
    cout << endl;
}

template <typename C, class T> void findit(const C& c, T val) {
    cout << "Trying find() on value " << val << endl;
    auto result = c.find(val);
    if (result != c.end()) {
        cout << "Element found: "; print_elem(*result); cout << endl;
    } else {
        cout << "Element not found." << endl;
    }
}

int main()
{
    multiset<int> s1({ 40, 45 });
    cout << "The starting multiset s1 is: " << endl;
    print_collection(s1);

    vector<int> v;
    v.push_back(43);
    v.push_back(41);
    v.push_back(46);
    v.push_back(42);
    v.push_back(44);
    v.push_back(44); // attempt a duplicate

    cout << "Inserting the following vector data into s1: " << endl;
    print_collection(v);

    s1.insert(v.begin(), v.end());

    cout << "The modified multiset s1 is: " << endl;
    print_collection(s1);
    cout << endl;
    findit(s1, 45);
    findit(s1, 6);
}
```

## <a name="get_allocator"></a>  multiset::get_allocator

multiset の構築に使用されるアロケーター オブジェクトのコピーを返します。

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>戻り値

multiset で使用されるアロケーター。

### <a name="remarks"></a>Remarks

multiset クラスのアロケーターは、クラスがどのようにストレージを管理するかを指定します。 C++ 標準ライブラリ コンテナー クラスで提供される既定のアロケーターは、ほとんどのプログラミング要件に対応しています。 独自のアロケーター クラスを作成して使用することは、C++ における高度な作業の 1 つです。

### <a name="example"></a>例

```cpp
// multiset_get_allocator.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int>::allocator_type ms1_Alloc;
   multiset <int>::allocator_type ms2_Alloc;
   multiset <double>::allocator_type ms3_Alloc;
   multiset <int>::allocator_type ms4_Alloc;

   // The following lines declare objects
   // that use the default allocator.
   multiset <int> ms1;
   multiset <int, allocator<int> > ms2;
   multiset <double, allocator<double> > ms3;

   cout << "The number of integers that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms2.max_size( ) << "." << endl;

   cout << "The number of doubles that can be allocated"
        << endl << "before free memory is exhausted: "
        << ms3.max_size( ) <<  "." << endl;

   // The following lines create a multiset ms4
   // with the allocator of multiset ms1
   ms1_Alloc = ms1.get_allocator( );
   multiset <int> ms4( less<int>( ), ms1_Alloc );
   ms4_Alloc = ms4.get_allocator( );

   // Two allocators are interchangeable if
   // storage allocated from each can be
   // deallocated with the other
   if( ms1_Alloc == ms4_Alloc )
   {
      cout << "Allocators are interchangeable."
           << endl;
   }
   else
   {
      cout << "Allocators are not interchangeable."
           << endl;
   }
}
```

## <a name="insert"></a>  multiset::insert

multiset に要素や要素範囲を挿入します。

```cpp
// (1) single element
pair<iterator, bool> insert(
    const value_type& Val);


// (2) single element, perfect forwarded
template <class ValTy>
pair<iterator, bool>
insert(
    ValTy&& Val);


// (3) single element with hint
iterator insert(
    const_iterator Where,
    const value_type& Val);


// (4) single element, perfect forwarded, with hint
template <class ValTy>
iterator insert(
    const_iterator Where,
    ValTy&& Val);


// (5) range
template <class InputIterator>
void insert(
    InputIterator First,
    InputIterator Last);


// (6) initializer list
void insert(
    initializer_list<value_type>
IList);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*val*|multiset に挿入する要素の値。|
|*Where*|正しい挿入ポイントの検索を開始する場所  (そのポイントの直前に場合*場所*、対数時間ではなく償却定数時間で実行できます)。|
|*ValTy*|Multiset の要素の構築に使用できる引数の型を指定するテンプレート パラメーター [value_type](../standard-library/map-class.md#value_type)、および完全転送*Val*を引数として。|
|*まずは*|コピーされる最初の要素の位置。|
|*前の*|コピーされる最後の要素の次の位置。|
|*InputIterator*|[入力反復子](../standard-library/input-iterator-tag-struct.md)の要件を満たすテンプレート関数の引数。この反復子は、[value_type](../standard-library/map-class.md#value_type) オブジェクトの構築に使用できる型の要素を指し示します。|
|*IList*|要素のコピー元の [initializer_list](../standard-library/initializer-list.md)。|

### <a name="return-value"></a>戻り値

単一要素の insert メンバー関数 (1) と (2) は、新しい要素が multiset に挿入された位置を指す反復子を返します。

単一要素とヒントのメンバー関数 (3) と (4) は、新しい要素が multiset に挿入された位置を指す反復子を返します。

### <a name="remarks"></a>Remarks

この関数では、ポインターや参照は無効になりません。ただし、コンテナーを指すすべての反復子が無効になる場合があります。

要素を 1 つだけ挿入するとき、例外がスローされるとコンテナーの状態は変更されません。 複数の要素を挿入するときに例外がスローされた場合、コンテナーの状態は未指定ですが、有効な状態になっています。

コンテナーの [value_type](../standard-library/map-class.md#value_type) はそのコンテナーに属する typedef であり、set の場合、`multiset<V>::value_type` は `const V` 型です。

範囲のメンバー関数 (5) は、multiset に要素値のシーケンスを挿入します。このシーケンスは、範囲 `[First, Last)` の反復子によってアドレス指定された各要素に対応します。したがって、`Last` は挿入されません。 コンテナーのメンバー関数 `end()` は、コンテナー内にある最後の要素の直後の位置を参照します。たとえば、ステートメント `s.insert(v.begin(), v.end());` は、`v` のすべての要素を `s` に挿入します。

初期化子リストのメンバー関数 (6) は、[initializer_list](../standard-library/initializer-list.md) を使用して multiset に要素をコピーします。

インプレースで構築された (つまり、コピーまたは移動操作が実行されない) 要素の挿入については、「[multiset::emplace](#emplace)」および「[multiset::emplace_hint](#emplace_hint)」をご覧ください。

### <a name="example"></a>例

```cpp
// multiset_insert.cpp
// compile with: /EHsc
#include <set>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

template <typename S> void print(const S& s) {
    cout << s.size() << " elements: ";

    for (const auto& p : s) {
        cout << "(" << p << ") ";
    }

    cout << endl;
}

int main()
{

    // insert single values
    multiset<int> s1;
    // call insert(const value_type&) version
    s1.insert({ 1, 10 });
    // call insert(ValTy&&) version
    s1.insert(20);

    cout << "The original multiset values of s1 are:" << endl;
    print(s1);

    // intentionally attempt a duplicate, single element
    s1.insert(1);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // single element, with hint
    s1.insert(s1.end(), 30);
    cout << "The modified multiset values of s1 are:" << endl;
    print(s1);
    cout << endl;

    // The templatized version inserting a jumbled range
    multiset<int> s2;
    vector<int> v;
    v.push_back(43);
    v.push_back(294);
    v.push_back(41);
    v.push_back(330);
    v.push_back(42);
    v.push_back(45);

    cout << "Inserting the following vector data into s2:" << endl;
    print(v);

    s2.insert(v.begin(), v.end());

    cout << "The modified multiset values of s2 are:" << endl;
    print(s2);
    cout << endl;

    // The templatized versions move-constructing elements
    multiset<string>  s3;
    string str1("blue"), str2("green");

    // single element
    s3.insert(move(str1));
    cout << "After the first move insertion, s3 contains:" << endl;
    print(s3);

    // single element with hint
    s3.insert(s3.end(), move(str2));
    cout << "After the second move insertion, s3 contains:" << endl;
    print(s3);
    cout << endl;

    multiset<int> s4;
    // Insert the elements from an initializer_list
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });
    cout << "After initializer_list insertion, s4 contains:" << endl;
    print(s4);
    cout << endl;
}

```

## <a name="iterator"></a>  multiset::iterator

multiset 内の任意の要素を読み取ることができる、定数の[双方向反復子](../standard-library/bidirectional-iterator-tag-struct.md)を提供する型。

```cpp
typedef implementation-defined iterator;
```

### <a name="example"></a>例

例をご覧ください[開始](#begin)宣言方法や使用方法の例については、`iterator`します。

## <a name="key_comp"></a>  multiset::key_comp

multiset 内のキーの並べ替えに使用する比較オブジェクトのコピーを取得します。

```cpp
key_compare key_comp() const;
```

### <a name="return-value"></a>戻り値

multiset が要素の並べ替えに使用する関数オブジェクトを返します。テンプレート パラメーター `Compare` です。

`Compare` の詳細については、[multiset クラス](../standard-library/multiset-class.md)のトピックのコメントのセクションをご覧ください。

### <a name="remarks"></a>Remarks

格納されているオブジェクトはメンバー関数を定義します。

**bool operator**( **const Key&** *x*, **const Key&** *y*);

これは、並べ替え順で *x* が厳密に *y* に先行する場合に true を返します。

[key_compare](#key_compare) および [value_compare](#value_compare) は両方ともテンプレート パラメーター `Compare` のシノニムです。 どちらもクラス set および multiset で使用でき、そこでは同一ですが、クラス map および multimap では異なるものなので互換性を保つようになっています。

### <a name="example"></a>例

```cpp
// multiset_key_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::key_compare kc1 = ms1.key_comp( ) ;
   bool result1 = kc1( 2, 3 ) ;
   if( result1 == true )
   {
      cout << "kc1( 2,3 ) returns value of true, "
           << "where kc1 is the function object of s1."
           << endl;
   }
   else
   {
      cout << "kc1( 2,3 ) returns value of false "
           << "where kc1 is the function object of ms1."
           << endl;
   }

   multiset <int, greater<int> > ms2;
   multiset <int, greater<int> >::key_compare kc2 = ms2.key_comp( ) ;
   bool result2 = kc2( 2, 3 ) ;
   if( result2 == true )
   {
      cout << "kc2( 2,3 ) returns value of true, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "kc2( 2,3 ) returns value of false, "
           << "where kc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.
kc2( 2,3 ) returns value of false, where kc2 is the function object of ms2.
```

## <a name="key_compare"></a>  multiset::key_compare

2 つの並べ替えキーを比較して、multiset 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供する型。

```cpp
typedef Compare key_compare;
```

### <a name="remarks"></a>Remarks

`key_compare` はテンプレート パラメーター `Compare` のシノニムです。

`Compare` の詳細については、[multiset クラス](../standard-library/multiset-class.md)のトピックのコメントのセクションをご覧ください。

### <a name="example"></a>例

`key_compare` の宣言方法や使用方法の例については、[key_comp](#key_comp) の例をご覧ください。

## <a name="key_type"></a>  multiset::key_type

並べ替えキーを比較して、multiset 内の 2 つの要素の相対順序を決定できる関数オブジェクトを提供する型。

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Remarks

`key_type` はテンプレート パラメーター `Key` のシノニムです。

`Key` の詳細については、[multiset クラス](../standard-library/multiset-class.md)のトピックのコメントのセクションをご覧ください。

### <a name="example"></a>例

`key_type` の宣言方法や使用方法の例については、[value_type](#value_type) の例をご覧ください。

## <a name="lower_bound"></a>  multiset::lower_bound

指定したキー以上のキーを持つ、multiset 内の最初の要素を指す反復子を返します。

```cpp
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```

### <a name="parameters"></a>パラメーター

*キー*検索対象の multiset の要素の並べ替えキーと比較される引数キー。

### <a name="return-value"></a>戻り値

`iterator`または`const_iterator`ことアドレスことと一致しない場合、multiset 内の最後の要素を指す場所を指す、またはされる引数キー以上のキーを持つ multiset 内の要素の位置は、キーの検出します。

### <a name="example"></a>例

```cpp
// multiset_lower_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.lower_bound( 20 );
   cout << "The element of multiset ms1 with a key of 20 is: "
        << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.lower_bound( 40 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
           << "with a key of 40." << endl;
   else
      cout << "The element of multiset ms1 with a key of 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a derefenced iterator addressing the location
   ms1_AcIter = ms1.end( );
   ms1_AcIter--;
   ms1_RcIter = ms1.lower_bound( *ms1_AcIter );
   cout << "The element of ms1 with a key matching "
        << "that of the last element is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The element of multiset ms1 with a key of 20 is: 20.
The multiset ms1 doesn't have an element with a key of 40.
The element of ms1 with a key matching that of the last element is: 30.
```

## <a name="max_size"></a>  multiset::max_size

multiset の最大長を返します。

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>戻り値

multiset の可能な最大長。

### <a name="example"></a>例

```cpp
// multiset_max_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::size_type i;

   i = ms1.max_size( );
   cout << "The maximum possible length "
        << "of the multiset is " << i << "." << endl;
}
```

## <a name="multiset"></a>  multiset::multiset

空の multiset を構築するか、他の multiset の全体または一部のコピーである multiset を構築します。

```cpp
multiset();

explicit multiset (
    const Compare& Comp);

multiset (
    const Compare& Comp,
    const Allocator& Al);

multiset(
    const multiset& Right);

multiset(
    multiset&& Right);

multiset(
    initializer_list<Type> IList);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp);

multiset(
    initializer_list<Type> IList,
    const Compare& Comp,
    const Allocator& Al);


template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp);

template <class InputIterator>
multiset (
    InputIterator First,
    InputIterator Last,
    const Compare& Comp,
    const Allocator& Al);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*Al*|この multiset オブジェクトに使用するストレージ アロケーター クラス。既定では、`Allocator` です。|
|*コンポジション*|multiset 内の要素の並べ替えに使用される、`const Compare` 型の比較関数。既定では `Compare` です。|
|*右*|構築される multiset のコピー元となる multiset。|
|*まずは*|コピーする要素範囲内の最初の要素の位置。|
|*前の*|コピーする要素範囲を超える最初の要素の位置。|
|*IList*|要素のコピー元の initializer_list。|

### <a name="remarks"></a>Remarks

すべてのコンストラクターは、アロケーター オブジェクトの型を格納します。このオブジェクトは multiset のメモリ ストレージを管理し、後で [get_allocator](#get_allocator) を呼び出して取得することができます。 代替アロケーターの代わりに使用されるクラス宣言やプリプロセス マクロでは、アロケーターのパラメーターが省略される場合があります。

すべてのコンストラクターは、それぞれの multiset を初期化します。

すべてのコンストラクターは、Compare 型の関数オブジェクトを格納します。このオブジェクトは multiset のキーの順序を確立するために使用され、後で [key_comp](#key_comp) を呼び出して取得することができます。

最初の 3 つのコンス トラクターを指定する空の初期 multiset、2 つ目の比較関数の種類を指定する (*Comp*) 明示的に要素と 3 番目の順序を確立する際に使用するアロケーターを指定する入力(*Al*) を使用します。 キーワード **explicit** は、特定の種類の自動型変換が実行されないようにします。

4 番目のコンス トラクターが multiset のコピーを指定します*右*します。

5 番目のコンス トラクターを移動して、multiset のコピーを指定します*右*します。

6 番目、7 番目、および 8 番目のコンストラクターは、要素のコピー元の initializer_list を指定します。

次の 3 つのコンストラクターは、multiset の範囲 `[First, Last)` をコピーします。下のコンストラクターになるほど、より明確に比較関数とアロケーターの型を指定します。

### <a name="example"></a>例

```cpp
// multiset_ctor.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main()
{
    using namespace std;
    //multiset <int>::iterator ms1_Iter, ms2_Iter, ms3_Iter;
    multiset <int>::iterator ms4_Iter, ms5_Iter, ms6_Iter, ms7_Iter;

    // Create an empty multiset ms0 of key type integer
    multiset <int> ms0;

    // Create an empty multiset ms1 with the key comparison
    // function of less than, then insert 4 elements
    multiset <int, less<int> > ms1;
    ms1.insert(10);
    ms1.insert(20);
    ms1.insert(20);
    ms1.insert(40);

    // Create an empty multiset ms2 with the key comparison
    // function of geater than, then insert 2 elements
    multiset <int, less<int> > ms2;
    ms2.insert(10);
    ms2.insert(20);

    // Create a multiset ms3 with the
    // allocator of multiset ms1
    multiset <int>::allocator_type ms1_Alloc;
    ms1_Alloc = ms1.get_allocator();
    multiset <int> ms3(less<int>(), ms1_Alloc);
    ms3.insert(30);

    // Create a copy, multiset ms4, of multiset ms1
    multiset <int> ms4(ms1);

    // Create a multiset ms5 by copying the range ms1[ first,  last)
    multiset <int>::const_iterator ms1_bcIter, ms1_ecIter;
    ms1_bcIter = ms1.begin();
    ms1_ecIter = ms1.begin();
    ms1_ecIter++;
    ms1_ecIter++;
    multiset <int> ms5(ms1_bcIter, ms1_ecIter);

    // Create a multiset ms6 by copying the range ms4[ first,  last)
    // and with the allocator of multiset ms2
    multiset <int>::allocator_type ms2_Alloc;
    ms2_Alloc = ms2.get_allocator();
    multiset <int> ms6(ms4.begin(), ++ms4.begin(), less<int>(), ms2_Alloc);

    cout << "ms1 =";
    for (auto i : ms1)
        cout << " " << i;
    cout << endl;

    cout << "ms2 =";
    for (auto i : ms2)
        cout << " " << i;
   cout << endl;

   cout << "ms3 =";
   for (auto i : ms3)
       cout << " " << i;
    cout << endl;

    cout << "ms4 =";
    for (auto i : ms4)
        cout << " " << i;
    cout << endl;

    cout << "ms5 =";
    for (auto i : ms5)
        cout << " " << i;
    cout << endl;

    cout << "ms6 =";
    for (auto i : ms6)
        cout << " " << i;
    cout << endl;

    // Create a multiset by moving ms5
    multiset<int> ms7(move(ms5));
    cout << "ms7 =";
    for (auto i : ms7)
        cout << " " << i;
    cout << endl;

    // Create a multiset with an initializer_list
    multiset<int> ms8({1, 2, 3, 4});
    cout << "ms8=";
    for (auto i : ms8)
        cout << " " << i;
    cout << endl;
}
```

## <a name="op_eq"></a>  multiset::operator=

この `multiset` の要素を、別の `multiset` の要素を使って置き換えます。

```cpp
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*right*|要素のコピー元または移動元である `multiset`。|

### <a name="remarks"></a>Remarks

`operator=` 要素を移動またはコピーされる*右*この`multiset`使用される参照型 (lvalue または rvalue) に応じて。 `operator=` が実行される前にこの `multiset` に存在する要素は、破棄されます。

### <a name="example"></a>例

```cpp
// multiset_operator_as.cpp
// compile with: /EHsc
#include <multiset>
#include <iostream>

int main( )
   {
   using namespace std;
   multiset<int> v1, v2, v3;
   multiset<int>::iterator iter;

   v1.insert(10);

   cout << "v1 = " ;
   for (iter = v1.begin(); iter != v1.end(); iter++)
      cout << *iter << " ";
   cout << endl;

   v2 = v1;
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;

// move v1 into v2
   v2.clear();
   v2 = move(v1);
   cout << "v2 = ";
   for (iter = v2.begin(); iter != v2.end(); iter++)
      cout << *iter << " ";
   cout << endl;
   }
```

## <a name="pointer"></a>  multiset::pointer

multiset 内の要素へのポインターを提供する型。

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Remarks

**pointer** 型を使って要素の値を変更することができます。

ほとんどの場合、multiset オブジェクト内の要素にアクセスするには[反復子](#iterator)を使用する必要があります。

## <a name="rbegin"></a>  multiset::rbegin

反転された multiset 内の最初の要素を示す反復子を返します。

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>戻り値

反転された multiset 内の最初の要素、または反転されていない multiset 内の最後の要素だったものを示す反転双方向反復子。

### <a name="remarks"></a>Remarks

`rbegin` は、rbegin が multiset で使用されるのと同様に、反転された multiset で使用されます。

`rbegin` の戻り値が `const_reverse_iterator` に割り当てられる場合は、multiset オブジェクトを変更できません。 `rbegin` の戻り値が `reverse_iterator` に割り当てられる場合は、multiset オブジェクトを変更できます。

`rbegin` を使用して、multiset 内を後方に向かって反復処理できます。

### <a name="example"></a>例

```cpp
// multiset_rbegin.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rbegin( );
   cout << "The first element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // begin can be used to start an interation
   // throught a multiset in a forward order
   cout << "The multiset is:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << endl;

   // rbegin can be used to start an interation
   // throught a multiset in a reverse order
   cout << "The reversed multiset is:";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << " " << *ms1_rIter;
   cout << endl;

   // A multiset element can be erased by dereferencing to its key
   ms1_rIter = ms1.rbegin( );
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rbegin( );
   cout << "After the erasure, the first element "
        << "in the reversed multiset is "<< *ms1_rIter << "."
        << endl;
}
```

```Output
The first element in the reversed multiset is 30.
The multiset is: 10 20 30
The reversed multiset is: 30 20 10
After the erasure, the first element in the reversed multiset is 20.
```

## <a name="reference"></a>  multiset::reference

multiset に格納されている要素への参照を提供する型。

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="example"></a>例

```cpp
// multiset_ref.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;

   ms1.insert( 10 );
   ms1.insert( 20 );

   // Declare and initialize a reference &Ref1 to the 1st element
   const int &Ref1 = *ms1.begin( );

   cout << "The first element in the multiset is "
        << Ref1 << "." << endl;
}
```

```Output
The first element in the multiset is 10.
```

## <a name="rend"></a>  multiset::rend

反転された multiset 内の最後の要素の次の位置を指す反復子を返します。

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>戻り値

反転された multiset 内の最後の要素の次の場所 (反転されていない multiset 内の最初の要素の前の場所) を指す逆順双方向反復子。

### <a name="remarks"></a>Remarks

`rend` は、[end](#end) が multiset で使用されるのと同様に、反転された multiset で使用されます。

`rend` の戻り値が `const_reverse_iterator` に割り当てられる場合は、multiset オブジェクトは変更できません。 `rend` の戻り値が `reverse_iterator` に割り当てられている場合は、multiset オブジェクトを変更できます。

`rend` を使用して、逆順反復子が multiset の末尾に達したかどうかをテストできます。

`rend` によって返された値は逆参照しないでください。

### <a name="example"></a>例

```cpp
// multiset_rend.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main() {
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;
   multiset <int>::reverse_iterator ms1_rIter;
   multiset <int>::const_reverse_iterator ms1_crIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_rIter = ms1.rend( ) ;
   ms1_rIter--;
   cout << "The last element in the reversed multiset is "
        << *ms1_rIter << "." << endl;

   // end can be used to terminate an interation
   // throught a multiset in a forward order
   cout << "The multiset is: ";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << *ms1_Iter << " ";
   cout << "." << endl;

   // rend can be used to terminate an interation
   // throught a multiset in a reverse order
   cout << "The reversed multiset is: ";
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )
      cout << *ms1_rIter << " ";
   cout << "." << endl;

   ms1_rIter = ms1.rend( );
   ms1_rIter--;
   ms1.erase ( *ms1_rIter );

   ms1_rIter = ms1.rend( );
   --ms1_rIter;
   cout << "After the erasure, the last element in the "
        << "reversed multiset is " << *ms1_rIter << "." << endl;
}
```

## <a name="reverse_iterator"></a>  multiset::reverse_iterator

反転された multiset 内の 1 つの要素の読み取りまたは変更ができる双方向反復子を提供する型。

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Remarks

`reverse_iterator` 型は、逆の順序で multiset を反復処理するために使用します。

### <a name="example"></a>例

`reverse_iterator` の宣言方法や使用方法の例については、[rbegin](#rbegin) の例をご覧ください。

## <a name="size"></a>  multiset::size

multiset 内の要素の数を返します。

```cpp
size_type size() const;
```

### <a name="return-value"></a>戻り値

multiset の現在の長さ。

### <a name="example"></a>例

```cpp
// multiset_size.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: size_type i;

   ms1.insert( 1 );
   i = ms1.size( );
   cout << "The multiset length is " << i << "." << endl;

   ms1.insert( 2 );
   i = ms1.size( );
   cout << "The multiset length is now " << i << "." << endl;
}
```

```Output
The multiset length is 1.
The multiset length is now 2.
```

## <a name="size_type"></a>  multiset::size_type

multiset 内の要素の数を表すことができる符号なし整数型。

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="example"></a>例

`size_type` の宣言方法や使用方法の例については、[size](#size) の例をご覧ください。

## <a name="swap"></a>  multiset::swap

2 つの multiset の要素を交換します。

```cpp
void swap(
    multiset<Key, Compare, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*適切な*ターゲットの multiset を交換する要素を提供する引数の multiset。

### <a name="remarks"></a>Remarks

メンバー関数は、要素を交換する 2 つの multiset において要素を指定している参照、ポインター、反復子を無効化することはありません。

### <a name="example"></a>例

```cpp
// multiset_swap.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1, ms2, ms3;
   multiset <int>::iterator ms1_Iter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );
   ms2.insert( 100 );
   ms2.insert( 200 );
   ms3.insert( 300 );

   cout << "The original multiset ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the member function version of swap
   ms1.swap( ms2 );

   cout << "After swapping with ms2, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;

   // This is the specialized template version of swap
   swap( ms1, ms3 );

   cout << "After swapping with ms3, list ms1 is:";
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout   << "." << endl;
}
```

```Output
The original multiset ms1 is: 10 20 30.
After swapping with ms2, list ms1 is: 100 200.
After swapping with ms3, list ms1 is: 300.
```

## <a name="upper_bound"></a>  multiset::upper_bound

指定したキーよりも大きいキーを持つ、multiset 内の最初の要素を指す反復子を返します。

```cpp
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```

### <a name="parameters"></a>パラメーター

*キー*検索対象の multiset の要素の並べ替えキーと比較される引数キー。

### <a name="return-value"></a>戻り値

引数キーより大きいキーを持つ multiset 内の要素の位置を指す、または、キーの一致が検出されない場合は multiset 内の最後の要素の次の位置を指す、**反復子**または `const_iterator`。

### <a name="example"></a>例

```cpp
// multiset_upper_bound.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;

   ms1.insert( 10 );
   ms1.insert( 20 );
   ms1.insert( 30 );

   ms1_RcIter = ms1.upper_bound( 20 );
   cout << "The first element of multiset ms1 with a key greater "
           << "than 20 is: " << *ms1_RcIter << "." << endl;

   ms1_RcIter = ms1.upper_bound( 30 );

   // If no match is found for the key, end( ) is returned
   if ( ms1_RcIter == ms1.end( ) )
      cout << "The multiset ms1 doesn't have an element "
              << "with a key greater than 30." << endl;
   else
      cout << "The element of multiset ms1 with a key > 40 is: "
           << *ms1_RcIter << "." << endl;

   // The element at a specific location in the multiset can be
   // found using a dereferenced iterator addressing the location
   ms1_AcIter = ms1.begin( );
   ms1_RcIter = ms1.upper_bound( *ms1_AcIter );
   cout << "The first element of ms1 with a key greater than"
        << endl << "that of the initial element of ms1 is: "
        << *ms1_RcIter << "." << endl;
}
```

```Output
The first element of multiset ms1 with a key greater than 20 is: 30.
The multiset ms1 doesn't have an element with a key greater than 30.
The first element of ms1 with a key greater than
that of the initial element of ms1 is: 20.
```

## <a name="value_comp"></a>  multiset::value_comp

multiset 内の要素の値の並べ替えに使用する比較オブジェクトのコピーを取得します。

```cpp
value_compare value_comp() const;
```

### <a name="return-value"></a>戻り値

multiset が要素の並べ替えに使用する関数オブジェクトを返します。テンプレート パラメーター `Compare` です。

`Compare` の詳細については、[multiset クラス](../standard-library/multiset-class.md)のトピックのコメントのセクションをご覧ください。

### <a name="remarks"></a>Remarks

格納されているオブジェクトは以下のメンバー関数を定義します。

**bool operator**( **const Key&**`_xVal`, **const Key&**`_yVal`);

これは、並べ替え順で `_xVal` が `_yVal` に先行しかつ等しくない場合に true を返します。

[key_compare](#key_compare) および [value_compare](#value_compare) は両方ともテンプレート パラメーター `Compare` のシノニムです。 どちらもクラス set および multiset で使用でき、そこでは同一ですが、クラス map および multimap では異なるものなので互換性を保つようになっています。

### <a name="example"></a>例

```cpp
// multiset_value_comp.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;

   multiset <int, less<int> > ms1;
   multiset <int, less<int> >::value_compare vc1 = ms1.value_comp( );
   bool result1 = vc1( 2, 3 );
   if( result1 == true )
   {
      cout << "vc1( 2,3 ) returns value of true, "
           << "where vc1 is the function object of ms1."
           << endl;
   }
   else
   {
      cout << "vc1( 2,3 ) returns value of false, "
           << "where vc1 is the function object of ms1."
           << endl;
   }

   set <int, greater<int> > ms2;
   set<int, greater<int> >::value_compare vc2 = ms2.value_comp( );
   bool result2 = vc2( 2, 3 );
   if( result2 == true )
   {
      cout << "vc2( 2,3 ) returns value of true, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
   else
   {
      cout << "vc2( 2,3 ) returns value of false, "
           << "where vc2 is the function object of ms2."
           << endl;
   }
}
```

```Output
vc1( 2,3 ) returns value of true, where vc1 is the function object of ms1.
vc2( 2,3 ) returns value of false, where vc2 is the function object of ms2.
```

## <a name="value_compare"></a>  multiset::value_compare

2 つの並べ替えキーを比較して multiset 内での相対順序を決定できる関数オブジェクトを提供する型。

```cpp
typedef key_compare value_compare;
```

### <a name="remarks"></a>Remarks

`value_compare` はテンプレート パラメーター `Compare` のシノニムです。

なお両方[key_compare](#key_compare)と`value_compare`テンプレート パラメーターのシノニムで`Compare`します。 どちらもクラス set および multiset で使用でき、そこでは同一ですが、クラス map および multimap では異なるものなので互換性を保つようになっています。

`Compare` の詳細については、[multiset クラス](../standard-library/multiset-class.md)のトピックのコメントのセクションをご覧ください。

### <a name="example"></a>例

`value_compare` の宣言方法や使用方法の例については、[value_comp](#value_comp) の例をご覧ください。

## <a name="value_type"></a>  multiset::value_type

要素としての値として、容量が multiset として格納されるオブジェクトを表す型。

```cpp
typedef Key value_type;
```

### <a name="remarks"></a>Remarks

`value_type` はテンプレート パラメーター `Key` のシノニムです。

なお両方[key_type](#key_type)と`value_type`テンプレート パラメーターのシノニムで`Key`します。 どちらもクラス set および multiset で使用でき、そこでは同一ですが、クラス map および multimap では異なるものなので互換性を保つようになっています。

`Key` の詳細については、このトピックのコメントのセクションをご覧ください。

### <a name="example"></a>例

```cpp
// multiset_value_type.cpp
// compile with: /EHsc
#include <set>
#include <iostream>

int main( )
{
   using namespace std;
   multiset <int> ms1;
   multiset <int>::iterator ms1_Iter;

   multiset <int> :: value_type svt_Int;   // Declare value_type
   svt_Int = 10;             // Initialize value_type

   multiset <int> :: key_type skt_Int;   // Declare key_type
   skt_Int = 20;             // Initialize key_type

   ms1.insert( svt_Int );         // Insert value into s1
   ms1.insert( skt_Int );         // Insert key into s1

   // A multiset accepts key_types or value_types as elements
   cout << "The multiset has elements:";
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )
      cout << " " << *ms1_Iter;
   cout << "." << endl;
}
```

```Output
The multiset has elements: 10 20.
```

## <a name="see-also"></a>関連項目

[\<設定 > メンバー](http://msdn.microsoft.com/0c2d57c0-173f-4204-b579-c5f06aad8b95)<br/>
[コンテナー](../cpp/containers-modern-cpp.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
