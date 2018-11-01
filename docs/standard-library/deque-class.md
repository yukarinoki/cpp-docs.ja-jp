---
title: deque クラス
ms.date: 11/04/2016
f1_keywords:
- deque/std::deque
- deque/std::deque::allocator_type
- deque/std::deque::const_iterator
- deque/std::deque::const_pointer
- deque/std::deque::const_reference
- deque/std::deque::const_reverse_iterator
- deque/std::deque::difference_type
- deque/std::deque::iterator
- deque/std::deque::pointer
- deque/std::deque::reference
- deque/std::deque::reverse_iterator
- deque/std::deque::size_type
- deque/std::deque::value_type
- deque/std::deque::assign
- deque/std::deque::at
- deque/std::deque::back
- deque/std::deque::begin
- deque/std::deque::cbegin
- deque/std::deque::cend
- deque/std::deque::clear
- deque/std::deque::crbegin
- deque/std::deque::crend
- deque/std::deque::emplace
- deque/std::deque::emplace_back
- deque/std::deque::emplace_front
- deque/std::deque::empty
- deque/std::deque::end
- deque/std::deque::erase
- deque/std::deque::front
- deque/std::deque::get_allocator
- deque/std::deque::insert
- deque/std::deque::max_size
- deque/std::deque::pop_back
- deque/std::deque::pop_front
- deque/std::deque::push_back
- deque/std::deque::push_front
- deque/std::deque::rbegin
- deque/std::deque::rend
- deque/std::deque::resize
- deque/std::deque::shrink_to_fit
- deque/std::deque::size
- deque/std::deque::swap
helpviewer_keywords:
- std::deque [C++]
- std::deque [C++], allocator_type
- std::deque [C++], const_iterator
- std::deque [C++], const_pointer
- std::deque [C++], const_reference
- std::deque [C++], const_reverse_iterator
- std::deque [C++], difference_type
- std::deque [C++], iterator
- std::deque [C++], pointer
- std::deque [C++], reference
- std::deque [C++], reverse_iterator
- std::deque [C++], size_type
- std::deque [C++], value_type
- std::deque [C++], assign
- std::deque [C++], at
- std::deque [C++], back
- std::deque [C++], begin
- std::deque [C++], cbegin
- std::deque [C++], cend
- std::deque [C++], clear
- std::deque [C++], crbegin
- std::deque [C++], crend
- std::deque [C++], emplace
- std::deque [C++], emplace_back
- std::deque [C++], emplace_front
- std::deque [C++], empty
- std::deque [C++], end
- std::deque [C++], erase
- std::deque [C++], front
- std::deque [C++], get_allocator
- std::deque [C++], insert
- std::deque [C++], max_size
- std::deque [C++], pop_back
- std::deque [C++], pop_front
- std::deque [C++], push_back
- std::deque [C++], push_front
- std::deque [C++], rbegin
- std::deque [C++], rend
- std::deque [C++], resize
- std::deque [C++], shrink_to_fit
- std::deque [C++], size
- std::deque [C++], swap
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
ms.openlocfilehash: 0d411344e20c6ef42d8af32e9a1adc448b73584c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619883"
---
# <a name="deque-class"></a>deque クラス

特定の型の要素をベクターのような線形の配置に整列し、任意の要素への高速なランダム アクセス、およびコンテナーの後ろでの効率的な挿入と削除を行えるようにします。 ただし、ベクターとは異なり、`deque` クラスは、コンテナーの前での効率的な挿入と削除もサポートします。

## <a name="syntax"></a>構文

```unstlib
template <class Type, class Allocator =allocator<Type>>
class deque
```

### <a name="parameters"></a>パラメーター

*Type*<br/>
deque に格納される要素のデータ型。

*アロケーター*<br/>
メモリの deque の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能で、既定値は**アロケーター\<型 >** します。

## <a name="remarks"></a>Remarks

一般的に、コンテナー型の選択は、アプリケーションにおいて必要な検索および挿入の種類に基づいている必要があります。 [ベクター](../standard-library/vector-class.md)は、任意の要素へのランダム アクセスが優先事項であり、要素の挿入または削除がシーケンスの最後にのみ必要な場合に、シーケンスを管理するための推奨されるコンテナーです。 リスト コンテナーでは、シーケンス内の任意の位置における (定数時間での) 効率的な挿入と削除が優先事項である場合に、より優れたパフォーマンスになります。 シーケンスの途中でこのような操作を行うには、シーケンス (線形時間) 内の要素数に比例した要素のコピーおよび割り当てが必要になります。

deque の再割り当ては、メンバー関数がシーケンスの要素を挿入または消去する必要がある場合に発生します。

- 要素が空のシーケンスに挿入された場合、または空のシーケンスを残すために要素が消去された場合は、[begin](#begin) および [end](#end) によって以前に返された反復子が無効になります。

- 要素が deque の最初の位置に挿入された場合は、既存の要素を指定するすべての反復子 (参照を除く) が無効になります。

- 要素が deque の末尾に挿入された場合は、[end](#end) および既存の要素を指定するすべての反復子 (参照を除く) が無効になります。

- 要素が deque の前で消去された場合は、その反復子と消去された要素へ参照のみが無効になります。

- 最後の要素が deque の末尾から消去された場合は、最後の要素への反復子と消去された要素への参照のみが無効になります。

それ以外の場合、要素を挿入または消去すると、すべての反復子および参照が無効になります。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[deque](#deque)|`deque` を構築します。 新しい内容を設定する複数のコンス トラクターが用意されて`deque`さまざまな方法で: 空の場合に空の要素数を指定して読み込まれます移動またはコピーから別の内容を`deque`; 内容をコピーしたり、反復子を使用して移動し、。1 つの要素にコピー、 `deque` `count`時間。 一部のコンストラクターでは、要素を作成するためのカスタムの `allocator` を使用できます。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[allocator_type](#allocator_type)|`allocator` オブジェクトの `deque` クラスを表す型。|
|[const_iterator](#const_iterator)|`deque` 内の要素にアクセスし、読み取ることができるランダム アクセス反復子を `const` として提供する型。|
|[const_pointer](#const_pointer)|`deque` 内の要素へのポインターを `const.` として提供する型。|
|[const_reference](#const_reference)|読み取りと他の操作の実行のために、`deque` 内の要素への参照を `const.` として提供する型。|
|[const_reverse_iterator](#const_reverse_iterator)|ランダム アクセス反復子を提供する型がアクセスし、内の要素を読み取ることができます、`deque`として**const**します。 deque は逆に表示されます。 詳しくは、「[reverse_iterator クラス](../standard-library/reverse-iterator-class.md)」をご覧ください。|
|[difference_type](#difference_type)|同じ `deque` 内の要素を参照する 2 つのランダム アクセス反復子の違いを提供する型。|
|[Iterator](#iterator)|`deque` 内の任意の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。|
|[pointer](#pointer)|`deque` 内の要素へのポインターを提供する型。|
|[reference](#reference)|`deque` に格納されている要素への参照を提供する型。|
|[reverse_iterator](#reverse_iterator)|`deque` 内の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。 deque は逆の順序で表示されます。|
|[size_type](#size_type)|`deque` 内の要素の数をカウントする型。|
|[value_type](#value_type)|`deque` に格納されているデータ型を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[assign](#assign)|`deque` から要素を消去し、対象の `deque` に要素の新しいシーケンスをコピーします。|
|[at](#at)|`deque` 内の指定した位置にある要素への参照を返します。|
|[back](#back)|`deque` の最後の要素への参照を返します。|
|[begin](#begin)|`deque` 内の最初の要素を示すランダム アクセス反復子を返します。|
|[cbegin](#cbegin)|`deque` 内の最初の要素への定数反復子を返します。|
|[cend](#cend)|ランダム アクセスを返します**const**の末尾の次の位置を指す反復子、`deque`します。|
|[clear](#clear)|`deque` のすべての要素を消去します。|
|[crbegin](#crbegin)|`deque` 内の最初の要素へのランダム アクセス定数反復子を返します。|
|[crend](#crend)|`deque` 内の最初の要素へのランダム アクセス定数反復子を返します。|
|[emplace](#emplace)|指定した位置において、構築された要素を `deque` の適切な場所に挿入します。|
|[emplace_back](#emplace_back)|構築された要素を `deque` の末尾の適切な場所に追加します。|
|[emplace_front](#emplace_front)|構築された要素を `deque` の先頭の適切な場所に追加します。|
|[empty](#empty)|返します**true**場合、 `deque` 0 個の要素を含むと**false** 1 つまたは複数の要素が含まれている場合。|
|[end](#end)|`deque` の末尾の次の位置を指し示すランダム アクセス反復子を返します。|
|[erase](#erase)|指定した位置から `deque` の要素または要素範囲を削除します。|
|[front](#front)|`deque` 内の最初の要素への参照を返します。|
|[get_allocator](#get_allocator)|`allocator` の構築に使用される `deque` オブジェクトのコピーを返します。|
|[insert](#insert)|指定した位置において、`deque` に単一の要素、複数の要素、または要素の範囲を挿入します。|
|[max_size](#max_size)|`deque` の可能な最大長を返します。|
|[pop_back](#pop_back)|`deque` の末尾の要素を消去します。|
|[pop_front](#pop_front)|`deque` の先頭の要素を消去します。|
|[push_back](#push_back)|`deque` の末尾に要素を追加します。|
|[push_front](#push_front)|`deque` の先頭に要素を追加します。|
|[rbegin](#rbegin)|逆順の `deque` 内の最初の要素へのランダム アクセス反復子を返します。|
|[rend](#rend)|逆順の `deque` 内の最後の要素の次の位置を指し示すランダム アクセス反復子を返します。|
|[resize](#resize)|`deque` の新しいサイズを指定します。|
|[shrink_to_fit](#shrink_to_fit)|余分なキャパシティを破棄します。|
|[size](#size)|`deque` 内の要素数を返します。|
|[swap](#swap)|2 つの `deque` の要素を交換します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator&#91;&#93;](#op_at)|指定した位置における `deque` 要素への参照を返します。|
|[operator=](#op_eq)|別の `deque` のコピーで `deque` の要素を置き換えます。|

## <a name="requirements"></a>必要条件

**ヘッダー**: \<deque>

## <a name="allocator_type"></a>  deque::allocator_type

deque オブジェクトのアロケーター クラスを表す型。

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Remarks

`allocator_type` はテンプレート パラメーター `Allocator` のシノニムです。

### <a name="example"></a>例

[get_allocator](#get_allocator) の例をご覧ください。

## <a name="assign"></a>  deque::assign

deque から要素を消去し、対象の deque に要素の新しいセットをコピーします。

```cpp
template <class InputIterator>
void assign(
    InputIterator First,
    InputIterator Last);

void assign(
    size_type Count,
    const Type& Val);

void assign(initializer_list<Type> IList);
```

### <a name="parameters"></a>パラメーター

*まずは*<br/>
deque 引数からコピーされる要素範囲内の最初の要素の位置。

*前の*<br/>
deque 引数からコピーされる要素範囲を超える最初の要素の位置。

*カウント*<br/>
deque に挿入される要素のコピーの数。

*val*<br/>
deque に挿入される要素の値。

*IList*<br/>
deque に挿入される initializer_list。

### <a name="remarks"></a>Remarks

対象の deque 内にある既存の要素が消去されると、`assign` によって、元の deque または他の deque からコピーされる指定の要素範囲が対象の deque に挿入されるか、指定した値の新しい要素のコピーが対象の deque に挿入されます。

### <a name="example"></a>例

```cpp
// deque_assign.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <initializer_list>

int main()
{
    using namespace std;
    deque <int> c1, c2;
    deque <int>::const_iterator cIter;

    c1.push_back(10);
    c1.push_back(20);
    c1.push_back(30);
    c2.push_back(40);
    c2.push_back(50);
    c2.push_back(60);

    deque<int> d1{ 1, 2, 3, 4 };
    initializer_list<int> iList{ 5, 6, 7, 8 };
    d1.assign(iList);

    cout << "d1 = ";
    for (int i : d1)
        cout << i;
    cout << endl;

    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(++c2.begin(), c2.end());
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

    c1.assign(7, 4);
    cout << "c1 =";
    for (int i : c1)
        cout << i;
    cout << endl;

}

```

```Output
d1 = 5678c1 =102030c1 =5060c1 =4444444
```

## <a name="at"></a>  deque::at

deque 内の指定位置にある要素への参照を返します。

```cpp
reference at(size_type pos);

const_reference at(size_type pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
deque 内で参照する要素を示す添字 (または位置の番号)。

### <a name="return-value"></a>戻り値

場合*pos* 、deque のサイズより大きい`at`例外をスローします。

### <a name="return-value"></a>戻り値

`at` の戻り値が `const_reference` に割り当てられている場合、deque オブジェクトを変更することはできません。 `at` の戻り値が `reference` に割り当てられている場合、deque オブジェクトを変更できます。

### <a name="example"></a>例

```cpp
// deque_at.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int& i = c1.at( 0 );
   int& j = c1.at( 1 );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="back"></a>  deque::back

deque の最後の要素への参照を返します。

```cpp
reference back();
const_reference back() const;
```

### <a name="return-value"></a>戻り値

deque の最後の要素。 deque が空の場合、戻り値は定義されません。

### <a name="remarks"></a>Remarks

`back` の戻り値が `const_reference` に割り当てられている場合、deque オブジェクトを変更することはできません。 `back` の戻り値が `reference` に割り当てられている場合、deque オブジェクトを変更できます。

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) を 1 または 2 に定義してコンパイルすると、空の deque 内の要素にアクセスしようとした場合に実行時エラーが発生します。  詳しくは、「[チェックを行う反復子](../standard-library/checked-iterators.md)」をご覧ください。

### <a name="example"></a>例

```cpp
// deque_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.back( );
   const int& ii = c1.front( );

   cout << "The last integer of c1 is " << i << endl;
   i--;
   cout << "The next-to-last integer of c1 is " << ii << endl;
}
```

```Output
The last integer of c1 is 11
The next-to-last integer of c1 is 10
```

## <a name="begin"></a>  deque::begin

deque の 1 つ目の要素を示す反復子を返します。

```cpp
const_iterator begin() const;
iterator begin();
```

### <a name="return-value"></a>戻り値

deque 内の最初の要素、または空の deque の次の位置を指すランダム アクセス反復子。

### <a name="remarks"></a>Remarks

`begin` の戻り値が `const_iterator` に割り当てられている場合、deque オブジェクトを変更することはできません。 場合の戻り値`begin`に割り当てられている、 `iterator`、deque オブジェクトを変更できます。

### <a name="example"></a>例

```cpp
// deque_begin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::const_iterator c1_cIter;

   c1.push_back( 1 );
   c1.push_back( 2 );

   c1_Iter = c1.begin( );
   cout << "The first element of c1 is " << *c1_Iter << endl;

*c1_Iter = 20;
   c1_Iter = c1.begin( );
   cout << "The first element of c1 is now " << *c1_Iter << endl;

   // The following line would be an error because iterator is const
   // *c1_cIter = 200;
}
```

```Output
The first element of c1 is 1
The first element of c1 is now 20
```

## <a name="cbegin"></a>  deque::cbegin

返します、 **const**範囲の最初の要素を指す反復子。

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>戻り値

A **const**最初の要素の範囲、または空の範囲の末尾の次の場所を指すランダム アクセス反復子 (空の範囲、 `cbegin() == cend()`)。

### <a name="remarks"></a>Remarks

`cbegin` の戻り値で範囲内の要素を変更することはできません。

`begin()` メンバー関数の代わりにこのメンバー関数を使用して、戻り値が `const_iterator` になることを保証できます。 通常は、次の例に示すように [auto](../cpp/auto-cpp.md) 型推論キーワードと共に使用します。 この例では、`Container` は `begin()` と `cbegin()` をサポートする任意の種類の変更可能な (非 `const`) コンテナーであるものとします。

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  deque::cend

返します、 **const**範囲の最後の要素の次の位置を指す反復子。

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>戻り値

範囲の末尾の次の位置を指し示すランダム アクセス反復子。

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

## <a name="clear"></a>  deque::clear

deque のすべての要素を消去します。

```cpp
void clear();
```

### <a name="example"></a>例

```cpp
// deque_clear.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   cout << "The size of the deque is initially " << c1.size( ) << endl;
   c1.clear( );
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;
}
```

```Output
The size of the deque is initially 3
The size of the deque after clearing is 0
```

## <a name="const_iterator"></a>  deque::const_iterator

deque 内の **const** 要素にアクセスし、読み取ることができるランダム アクセス反復子を提供する型。

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Remarks

`const_iterator` 型で要素の値を変更することはできません。

### <a name="example"></a>例

[back](#back) の例を参照してください。

## <a name="const_pointer"></a>  deque::const_pointer

ポインターを**const** deque 内の要素。

```cpp
typedef typename Allocator::const_pointer const_pointer;
```

### <a name="remarks"></a>Remarks

`const_pointer` 型で要素の値を変更することはできません。 deque の要素にアクセスするには、[iterator](#iterator) の方がより一般的に使われます。

## <a name="const_reference"></a>  deque::const_reference

読み取りと **const** 操作の実行のために deque に格納された **const** 要素への参照を提供する型。

```cpp
typedef typename Allocator::const_reference const_reference;
```

### <a name="remarks"></a>Remarks

`const_reference` 型で要素の値を変更することはできません。

### <a name="example"></a>例

```cpp
// deque_const_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const deque <int> c2 = c1;
   const int &i = c2.front( );
   const int &j = c2.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;

   // The following line would cause an error as c2 is const
   // c2.push_back( 30 );
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="const_reverse_iterator"></a>  deque::const_reverse_iterator

deque 内の任意の **const** 要素を読み取ることができるランダム アクセス反復子を提供する型。

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Remarks

`const_reverse_iterator` 型は要素の値を変更できず、逆の順序で deque を反復処理するために使用します。

### <a name="example"></a>例

反復子の宣言方法や使用方法の例については、[rbegin](#rbegin) の例をご覧ください。

## <a name="crbegin"></a>  deque::crbegin

反転された deque 内の最初の要素への定数反復子を返します。

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>戻り値

反転された [deque](../standard-library/deque-class.md) の最初の要素を指すか、反転されていない `deque` の最後の要素だったものを指す、定数逆順ランダム アクセス反復子。

### <a name="remarks"></a>Remarks

戻り値が `crbegin` の場合、`deque` オブジェクトは変更できません。

### <a name="example"></a>例

```cpp
// deque_crbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator v1_Iter;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   v1_Iter = v1.begin( );
   cout << "The first element of deque is "
        << *v1_Iter << "." << endl;

   v1_rIter = v1.crbegin( );
   cout << "The first element of the reversed deque is "
        << *v1_rIter << "." << endl;
}
```

```Output
The first element of deque is 1.
The first element of the reversed deque is 2.
```

## <a name="crend"></a>  deque::crend

反転された deque 内の最後の要素の次の位置を指す定数反復子を返します。

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>戻り値

反転された [deque](../standard-library/deque-class.md) 内の最後の要素の次の位置 (通常の順序の deque 内の最初の要素の前の位置) を指す定数逆順ランダム アクセス反復子。

### <a name="remarks"></a>Remarks

`crend` は、[array::cend](../standard-library/array-class-stl.md#cend) が `deque` で使われるときと同様の方法で、反転された `deque` で使われます。

戻り値が (適切にデクリメントされた) `crend` の場合、`deque` オブジェクトは変更できません。

`crend` を使って、逆順反復子が deque の末尾に達したかどうかをテストできます。

`crend` によって返された値は逆参照しないでください。

### <a name="example"></a>例

```cpp
// deque_crend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::const_reverse_iterator v1_rIter;

   v1.push_back( 1 );
   v1.push_back( 2 );

   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )
      cout << *v1_rIter << endl;
}
```

```Output
2
1
```

## <a name="deque"></a>  deque::deque

特定のサイズ、特定の値の要素、または特定のアロケーターを持つ deque を構築します。あるいは他の deque の全体または一部のコピーとして構築します。

```cpp
deque();

explicit deque(const Allocator& Al);
explicit deque(size_type Count);
deque(size_type Count, const Type& Val);

deque(
    size_type Count,
    const Type& Val,
    const Allocator& Al);

deque(const deque& Right);

template <class InputIterator>
deque(InputIterator First,  InputIterator Last);

template <class InputIterator>
deque(
   InputIterator First,
   InputIterator Last,
   const Allocator& Al);

deque(initializer_list<value_type> IList, const Allocator& Al);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*Al*|このオブジェクトに対して使用するアロケーター クラス。|
|*カウント*|構築された deque 内の要素の数。|
|*val*|構築された deque の要素の値。|
|*右*|構築された deque がコピーになる元の deque。|
|*まずは*|コピーする要素範囲内の最初の要素の位置。|
|*前の*|コピーする要素範囲を超える最初の要素の位置。|
|* IList'|コピーされる initializer_list。|

### <a name="remarks"></a>Remarks

すべてのコンス トラクターは、アロケーター オブジェクトを格納 (*Al*) し、deque を初期化します。

最初の 2 つのコンストラクターは、空の初期 deque を指定し、2 番目のコンストラクターは、使用するアロケーターの型 (`_Al`) も指定します。

3 番目のコンストラクターは、`count` クラスの、指定された数 (`Type`) の既定値の要素を繰り返すことを指定します。

4 番目と 5 番目のコンス トラクターの繰り返しを指定する (*カウント*) の値の要素`val`します。

6 番目のコンス トラクターには、deque のコピーを示す*右*します。

7 番目と 8 番目のコンストラクターは、deque の範囲 `[First, Last)` をコピーします。

7 番目のコンス トラクターは、移動、deque*右*します。

8 番目のコンストラクターは、initializer_list の内容をコピーします。

コンストラクターでは、暫定的な再割り当てを実行しません。

### <a name="example"></a>例

```cpp
/ compile with: /EHsc
#include <deque>
#include <iostream>
#include <forward_list>

int main()
{
    using namespace std;

    forward_list<int> f1{ 1, 2, 3, 4 };

    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });

    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1(3);

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2(5, 2);

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3(3, 1, c2.get_allocator());

    // Create a copy, deque c4, of deque c2
    deque <int> c4(c2);

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    deque <int> c5(c4.begin(), c4_Iter);

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin();
    c4_Iter++;
    c4_Iter++;
    c4_Iter++;
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

    initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for (int i : c1)
        cout << i << " ";
    cout << endl;

    cout << "c2 = ";
    for (int i : c2)
        cout << i << " ";
    cout << endl;

    cout << "c3 = ";
    for (int i : c3)
        cout << i << " ";
    cout << endl;

    cout << "c4 = ";
    for (int i : c4)
        cout << i << " ";
    cout << endl;

    cout << "c5 = ";
    for (int i : c5)
        cout << i << " ";
    cout << endl;

    cout << "c6 = ";
    for (int i : c6)
        cout << i << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7(move(c6));
    deque <int>::iterator c7_Iter;

    cout << "c7 =";
    for (int i : c7)
        cout << i << " ";
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    for (int i : c9)
        cout << i << " ";
    cout << endl;

    int x = 3;
}
// deque_deque.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
    using namespace std;
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;

    // Create an empty deque c0
    deque <int> c0;

    // Create a deque c1 with 3 elements of default value 0
    deque <int> c1( 3 );

    // Create a deque c2 with 5 elements of value 2
    deque <int> c2( 5, 2 );

    // Create a deque c3 with 3 elements of value 1 and with the
    // allocator of deque c2
    deque <int> c3( 3, 1, c2.get_allocator( ) );

    // Create a copy, deque c4, of deque c2
    deque <int> c4( c2 );

    // Create a deque c5 by copying the range c4[ first,  last)
    c4_Iter = c4.begin( );
    c4_Iter++;
    c4_Iter++;
    deque <int> c5( c4.begin( ), c4_Iter );

    // Create a deque c6 by copying the range c4[ first,  last) and
    // c2 with the allocator of deque
    c4_Iter = c4.begin( );
   c4_Iter++;
   c4_Iter++;
   c4_Iter++;
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );

    // Create a deque c8 by copying the contents of an initializer_list
    // using brace initialization
    deque<int> c8({ 1, 2, 3, 4 });

        initializer_list<int> iList{ 5, 6, 7, 8 };
    deque<int> c9( iList);

    cout << "c1 = ";
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
        cout << *c1_Iter << " ";
    cout << endl;

    cout << "c2 = ";
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )
        cout << *c2_Iter << " ";
    cout << endl;

    cout << "c3 = ";
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )
        cout << *c3_Iter << " ";
    cout << endl;

    cout << "c4 = ";
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )
        cout << *c4_Iter << " ";
    cout << endl;

    cout << "c5 = ";
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )
        cout << *c5_Iter << " ";
    cout << endl;

    cout << "c6 = ";
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )
        cout << *c6_Iter << " ";
    cout << endl;

    // Move deque c6 to deque c7
    deque <int> c7( move(c6) );
    deque <int>::iterator c7_Iter;

    cout << "c7 =" ;
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )
        cout << " " << *c7_Iter;
    cout << endl;

    cout << "c8 = ";
    for (int i : c8)
        cout << i << " ";
    cout << endl;

    cout << "c9 = ";
    or (int i : c9)
        cout << i << " ";
    cout << endl;
}
```

## <a name="difference_type"></a>  deque::difference_type

同じ deque 内の要素を参照する 2 反復子の違いを提供する型。

```cpp
typedef typename Allocator::difference_type difference_type;
```

### <a name="remarks"></a>Remarks

`difference_type` は、2 つのポインターの間にある要素数と言い換えることもできます。

### <a name="example"></a>例

```cpp
// deque_diff_type.cpp
// compile with: /EHsc
#include <iostream>
#include <deque>
#include <algorithm>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter, c2_Iter;

   c1.push_back( 30 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 10 );
   c1.push_back( 30 );
   c1.push_back( 20 );

   c1_Iter = c1.begin( );
   c2_Iter = c1.end( );

   deque <int>::difference_type df_typ1, df_typ2, df_typ3;

   df_typ1 = count( c1_Iter, c2_Iter, 10 );
   df_typ2 = count( c1_Iter, c2_Iter, 20 );
   df_typ3 = count( c1_Iter, c2_Iter, 30 );
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";
}
```

```Output
The number '10' is in c1 collection 1 times.
The number '20' is in c1 collection 2 times.
The number '30' is in c1 collection 3 times.
```

## <a name="emplace"></a>  deque::emplace

指定した位置において、構築された要素を deque の適切な場所に挿入します。

```cpp
iterator emplace(
    const_iterator _Where,
    Type&& val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*_Where*|最初の要素を挿入する [deque](../standard-library/deque-class.md) 内の位置。|
|*val*|`deque` に挿入される要素の値。|

### <a name="return-value"></a>戻り値

この関数は、新しい要素が deque 内に挿入された位置を指す反復子を返します。

### <a name="remarks"></a>Remarks

挿入操作は負荷が高くなることがあります。`deque` のパフォーマンスに関する説明は `deque` を参照してください。

### <a name="example"></a>例

```cpp
// deque_emplace.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   deque <int>::iterator Iter;

   v1.push_back( 10 );
   v1.push_back( 20 );
   v1.push_back( 30 );

   cout << "v1 =" ;
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )
      cout << " " << *Iter;
   cout << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace( vv1.begin(), move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      {
      cout << "vv1[0] =";
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )
         cout << " " << *Iter;
      cout << endl;
      }
}
```

```Output
v1 = 10 20 30
vv1[0] = 10 20 30
```

## <a name="emplace_back"></a>  deque::emplace_back

その場で構築した要素を deque の末尾に追加します。

```cpp
void emplace_back(Type&& val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*val*|[deque](../standard-library/deque-class.md) の末尾に追加する要素。|

### <a name="example"></a>例

```cpp
// deque_emplace_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_back( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="emplace_front"></a>  deque::emplace_front

その場で構築した要素を deque の末尾に追加します。

```cpp
void emplace_front(Type&& val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*val*|[deque](../standard-library/deque-class.md) の先頭に追加する要素。|

### <a name="example"></a>例

```cpp
// deque_emplace_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;

   v1.push_back( 1 );
   if ( v1.size( ) != 0 )
      cout << "Last element: " << v1.back( ) << endl;

   v1.push_back( 2 );
   if ( v1.size( ) != 0 )
      cout << "New last element: " << v1.back( ) << endl;

// initialize a deque of deques by moving v1
   deque < deque <int> > vv1;

   vv1.emplace_front( move( v1 ) );
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )
      cout << "Moved last element: " << vv1[0].back( ) << endl;
}
```

```Output
Last element: 1
New last element: 2
Moved last element: 2
```

## <a name="empty"></a>  deque::empty

deque が空かどうかをテストします。

```cpp
bool empty() const;
```

### <a name="return-value"></a>戻り値

deque が空の場合は **true**、deque が空でない場合は **false**。

### <a name="example"></a>例

```cpp
// deque_empty.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   if ( c1.empty( ) )
      cout << "The deque is empty." << endl;
   else
      cout << "The deque is not empty." << endl;
}
```

```Output
The deque is not empty.
```

## <a name="end"></a>  deque::end

deque 内の最後の要素の次の位置を指す反復子を返します。

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>戻り値

deque 内の最後の要素の次の位置を指すランダム アクセス反復子。 deque が空の場合は、deque::end == deque::begin です。

### <a name="remarks"></a>Remarks

`end` 反復子が deque の末尾に達したかどうかをテストに使用されます。

### <a name="example"></a>例

```cpp
// deque_end.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_Iter = c1.end( );
   c1_Iter--;
   cout << "The last integer of c1 is " << *c1_Iter << endl;

   c1_Iter--;
   *c1_Iter = 400;
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;

   // If a const iterator had been declared instead with the line:
   // deque <int>::const_iterator c1_Iter;
   // an error would have resulted when inserting the 400

   cout << "The deque is now:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
}
```

```Output
The last integer of c1 is 30
The new next-to-last integer of c1 is 400
The deque is now: 10 400 30
```

## <a name="erase"></a>  deque::erase

指定した位置から deque 内の要素または要素範囲を削除します。

```cpp
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```

### <a name="parameters"></a>パラメーター

*_Where*<br/>
deque から削除する要素の位置。

*first*<br/>
deque から削除する最初の要素の位置。

*last*<br/>
deque から削除する最後の要素の次の位置。

### <a name="return-value"></a>戻り値

削除された要素の後に残る最初の要素を指定するランダム アクセス反復子。このような要素が存在しない場合は、deque の末尾へのポインター。

### <a name="remarks"></a>Remarks

`erase` は例外をスローしません。

### <a name="example"></a>例

```cpp
// deque_erase.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator Iter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );
   c1.push_back( 40 );
   c1.push_back( 50 );
   cout << "The initial deque is: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   c1.erase( c1.begin( ) );
   cout << "After erasing the first element, the deque becomes:  ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
   Iter = c1.begin( );
   Iter++;
   c1.erase( Iter, c1.end( ) );
   cout << "After erasing all elements but the first, deque becomes: ";
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )
      cout << *Iter << " ";
   cout << endl;
}
```

```Output
The initial deque is: 10 20 30 40 50
After erasing the first element, the deque becomes:  20 30 40 50
After erasing all elements but the first, deque becomes: 20
```

## <a name="front"></a>  deque::front

deque 内の最初の要素への参照を返します。

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>戻り値

deque が空の場合、戻り値は定義されません。

### <a name="remarks"></a>Remarks

`front` の戻り値が `const_reference` に割り当てられている場合、deque オブジェクトを変更することはできません。 `front` の戻り値が `reference` に割り当てられている場合、deque オブジェクトを変更できます。

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) を 1 または 2 に定義してコンパイルすると、空の deque 内の要素にアクセスしようとした場合に実行時エラーが発生します。  詳しくは、「[チェックを行う反復子](../standard-library/checked-iterators.md)」をご覧ください。

### <a name="example"></a>例

```cpp
// deque_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 11 );

   int& i = c1.front( );
   const int& ii = c1.front( );

   cout << "The first integer of c1 is " << i << endl;
   i++;
   cout << "The second integer of c1 is " << ii << endl;
}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 11
```

## <a name="get_allocator"></a>  deque::get_allocator

deque の構築に使用されるアロケーター オブジェクトのコピーを返します。

```cpp
Allocator get_allocator() const;
```

### <a name="return-value"></a>戻り値

deque で使われるアロケーター。

### <a name="remarks"></a>Remarks

deque クラスのアロケーターは、クラスがどのようにストレージを管理するかを指定します。 C++ 標準ライブラリ コンテナー クラスで提供される既定のアロケーターは、ほとんどのプログラミング要件に対応しています。 独自のアロケーター クラスを作成して使用することは、C++ における高度な作業の 1 つです。

### <a name="example"></a>例

```cpp
// deque_get_allocator.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects that use the default allocator.
   deque <int> c1;
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );

   // c3 will use the same allocator class as c1
   deque <int> c3( c1.get_allocator( ) );

   deque <int>::allocator_type xlst = c1.get_allocator( );
   // You can now call functions on the allocator class used by c1
}
```

## <a name="insert"></a>  deque::insert

deque の指定された位置に要素、複数の要素、または要素の範囲を挿入します。

```cpp
iterator insert(
    const_iterator Where,
    const Type& Val);

iterator insert(
    const_iterator Where,
    Type&& Val);

void insert(
    iterator Where,
    size_type Count,
    const Type& Val);

template <class InputIterator>
void insert(
    iterator Where,
    InputIterator First,
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>
IList);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*Where*|最初の要素が挿入される、ターゲット deque 内の位置。|
|*val*|deque に挿入される要素の値。|
|*カウント*|deque に挿入される要素の数。|
|*まずは*|コピーされる引数 deque の要素範囲内にある最初の要素の位置。|
|*前の*|コピーされる引数 deque の要素範囲外にある最初の要素の位置。|
|*IList*|挿入する要素の initializer_list。|

### <a name="return-value"></a>戻り値

最初の 2 つの insert 関数は、新しい要素が deque に挿入される位置を指す反復子を返します。

### <a name="remarks"></a>Remarks

どの挿入操作も、負荷が大きくなる場合があります。

## <a name="iterator"></a>  deque::iterator

deque 内の任意の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Remarks

型`iterator`要素の値を変更するために使用できます。

### <a name="example"></a>例

[begin](#begin) の例を参照してください。

## <a name="max_size"></a>  deque::max_size

deque の最大長を返します。

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>戻り値

deque の可能な最大長。

### <a name="example"></a>例

```cpp
// deque_max_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   i = c1.max_size( );
   cout << "The maximum possible length of the deque is " << i << "." << endl;
}
```

## <a name="op_at"></a>  deque::operator[]

指定した位置における deque 要素への参照を返します。

```cpp
reference operator[](size_type pos);

const_reference operator[](size_type pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
参照する deque 要素の位置。

### <a name="return-value"></a>戻り値

引数で指定した位置の要素への参照。 指定した位置が deque のサイズより大きい場合、結果は未定義になります。

### <a name="remarks"></a>Remarks

`operator[]` の戻り値が `const_reference` に割り当てられている場合、deque オブジェクトを変更することはできません。 `operator[]` の戻り値が `reference` に割り当てられている場合、deque オブジェクトを変更できます。

1 または 2 に定義された [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) を使ってコンパイルすると、deque の境界外の要素にアクセスしようとした場合にランタイム エラーが発生します。  詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md) 」を参照してください。

### <a name="example"></a>例

```cpp
// deque_op_ref.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   cout << "The first integer of c1 is " << c1[0] << endl;
   int& i = c1[1];
   cout << "The second integer of c1 is " << i << endl;

}
```

```Output
The first integer of c1 is 10
The second integer of c1 is 20
```

## <a name="op_eq"></a>  deque::operator=

別の deque の要素を使ってこの deque の要素を置き換えます。

```cpp
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*right*|新しい内容を提供する deque。|

### <a name="remarks"></a>Remarks

最初のオーバーライドからこの deque に要素をコピー*右*代入のソース。 2 番目のオーバーライドからこの deque に要素を移動する*右*します。

演算子の実行前にこの deque に格納されていた要素は削除されます。

### <a name="example"></a>例

```cpp
// deque_operator_as.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
using namespace std;

typedef deque<int> MyDeque;

template<typename MyDeque> struct S;

template<typename MyDeque> struct S<MyDeque&> {
  static void show( MyDeque& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
    cout << endl;
  }
};

template<typename MyDeque> struct S<MyDeque&&> {
  static void show( MyDeque&& d ) {
    MyDeque::const_iterator iter;
    for (iter = d.cbegin(); iter != d.cend(); iter++)
       cout << *iter << " ";
cout << " via unnamed rvalue reference " << endl;
  }
};

int main( )
{
   MyDeque d1, d2;

   d1.push_back(10);
   d1.push_back(20);
   d1.push_back(30);
   d1.push_back(40);
   d1.push_back(50);

   cout << "d1 = " ;
   S<MyDeque&>::show( d1 );

   d2 = d1;
   cout << "d2 = ";
   S<MyDeque&>::show( d2 );

   cout << "     ";
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );
}
```

## <a name="pointer"></a>  deque::pointer

[deque](../standard-library/deque-class.md) の要素へのポインターを提供します。

```unstlib
typedef typename Allocator::pointer pointer;
```

### <a name="remarks"></a>Remarks

型`pointer`要素の値を変更するために使用できます。 deque の要素にアクセスするには、[iterator](#iterator) の方がより一般的に使われます。

## <a name="pop_back"></a>  deque::pop_back

deque の末尾の要素を削除します。

```cpp
void pop_back();
```

### <a name="remarks"></a>Remarks

最後の要素は空でない必要があります。 `pop_back` は例外をスローしません。

### <a name="example"></a>例

```cpp
// deque_pop_back.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The last element is: " << c1.back( ) << endl;

   c1.pop_back( );
   cout << "After deleting the element at the end of the deque, the "
      "last element is: " << c1.back( ) << endl;
}
```

```Output
The first element is: 1
The last element is: 2
After deleting the element at the end of the deque, the last element is: 1
```

## <a name="pop_front"></a>  deque::pop_front

deque の先頭の要素を削除します。

```cpp
void pop_front();
```

### <a name="remarks"></a>Remarks

最初の要素は空でない必要があります。 `pop_front` は例外をスローしません。

### <a name="example"></a>例

```cpp
// deque_pop_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 1 );
   c1.push_back( 2 );
   cout << "The first element is: " << c1.front( ) << endl;
   cout << "The second element is: " << c1.back( ) << endl;

   c1.pop_front( );
   cout << "After deleting the element at the beginning of the "
      "deque, the first element is: " << c1.front( ) << endl;
}
```

```Output
The first element is: 1
The second element is: 2
After deleting the element at the beginning of the deque, the first element is: 2
```

## <a name="push_back"></a>  deque::push_back

deque の末尾に要素を追加します。

```cpp
void push_back(const Type& val);

void push_back(Type&& val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*val*|deque の末尾に追加する要素。|

### <a name="remarks"></a>Remarks

例外がスローされた場合、deque は変更されず、例外が再度スローされます。

## <a name="push_front"></a>  deque::push_front

deque の先頭に要素を追加します。

```cpp
void push_front(const Type& val);
void push_front(Type&& val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|-|-|
|*val*|deque の先頭に追加する要素。|

### <a name="remarks"></a>Remarks

例外がスローされた場合、deque は変更されず、例外が再度スローされます。

### <a name="example"></a>例

```cpp
// deque_push_front.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_front( 1 );
   if ( c1.size( ) != 0 )
      cout << "First element: " << c1.front( ) << endl;

   c1.push_front( 2 );
   if ( c1.size( ) != 0 )
      cout << "New first element: " << c1.front( ) << endl;

// move initialize a deque of strings
   deque <string> c2;
   string str("a");

   c2.push_front( move( str ) );
   cout << "Moved first element: " << c2.front( ) << endl;
}
```

```Output
First element: 1
New first element: 2
Moved first element: a
```

## <a name="rbegin"></a>  deque::rbegin

反転された deque の最初の要素への反復子を返します。

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>戻り値

反転された deque の最初の要素を指すか、反転されていない deque の最後の要素だったものを指す、逆順ランダム アクセス反復子。

### <a name="remarks"></a>Remarks

`rbegin` は、[begin](#begin) が deque で使われるように、反転された deque で使われます。

`rbegin` の戻り値が `const_reverse_iterator` に割り当てられている場合、deque オブジェクトを変更することはできません。 `rbegin` の戻り値が `reverse_iterator` に割り当てられている場合、deque オブジェクトを変更できます。

`rbegin` を使って、deque 内を後方に向かって反復処理できます。

### <a name="example"></a>例

```cpp
// deque_rbegin.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;

   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rbegin( );
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;

   cout << "The deque contains the elements: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << "in that order.";
   cout << endl;

   // rbegin can be used to iterate through a deque in reverse order
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rbegin( );
   *c1_rIter = 40;  // This would have caused an error if a
                    // const_reverse iterator had been declared as
                    // noted above
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;
}
```

```Output
Last element in the deque is 30.
The deque contains the elements: 10 20 30 in that order.
The reversed deque is: 30 20 10
Last element in deque is now 40.
```

## <a name="reference"></a>  deque::reference

deque に格納されている要素への参照を提供する型。

```cpp
typedef typename Allocator::reference reference;
```

### <a name="example"></a>例

```cpp
// deque_reference.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );

   const int &i = c1.front( );
   int &j = c1.back( );
   cout << "The first element is " << i << endl;
   cout << "The second element is " << j << endl;
}
```

```Output
The first element is 10
The second element is 20
```

## <a name="rend"></a>  deque::rend

反転された deque 内の最後の要素の次の位置を指す反復子を返します。

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>戻り値

反転された deque 内の最後の要素の次の位置 (通常の順序の deque 内の最初の要素の前の位置) を指す逆順ランダム アクセス反復子。

### <a name="remarks"></a>Remarks

`rend` は、[end](#end) が deque で使われるように、反転された deque で使われます。

`rend` の戻り値が `const_reverse_iterator` に割り当てられている場合、deque オブジェクトを変更することはできません。 `rend` の戻り値が `reverse_iterator` に割り当てられている場合、deque オブジェクトを変更できます。

`rend` を使って、逆順反復子が deque の末尾に達したかどうかをテストできます。

`rend` によって返された値は逆参照しないでください。

### <a name="example"></a>例

```cpp
// deque_rend.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;

   deque <int> c1;
   deque <int>::iterator c1_Iter;
   deque <int>::reverse_iterator c1_rIter;
   // If the following line had replaced the line above, an error
   // would have resulted in the line modifying an element
   // (commented below) because the iterator would have been const
   // deque <int>::const_reverse_iterator c1_rIter;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1_rIter = c1.rend( );
   c1_rIter --; // Decrementing a reverse iterator moves it forward
                // in the deque (to point to the first element here)
   cout << "The first element in the deque is: " << *c1_rIter << endl;

   cout << "The deque is: ";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << *c1_Iter << " ";
   cout << endl;

   // rend can be used to test if an iteration is through all of
   // the elements of a reversed deque
   cout << "The reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;

   c1_rIter = c1.rend( );
   c1_rIter--; // Decrementing the reverse iterator moves it backward
               // in the reversed deque (to the last element here)
   *c1_rIter = 40; // This modification of the last element would
                   // have caused an error if a const_reverse
                   // iterator had been declared (as noted above)
   cout << "The modified reversed deque is: ";
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )
      cout << *c1_rIter << " ";
   cout << endl;
}
```

```Output
The first element in the deque is: 10
The deque is: 10 20 30
The reversed deque is: 30 20 10
The modified reversed deque is: 30 20 40
```

## <a name="resize"></a>  deque::resize

deque の新しいサイズを指定します。

```cpp
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```

### <a name="parameters"></a>パラメーター

*_Newsize*<br/>
deque の新しいサイズ。

*val*<br/>
新しいサイズが元のサイズより大きい場合に、deque に追加される新しい要素の値。 この値を省略した場合、新しい要素にはそのクラスの既定値が割り当てられます。

### <a name="remarks"></a>Remarks

Deque のサイズが要求されたサイズより小さい場合 *_Newsize*、要求されたサイズに達するまで、deque に要素が追加されます。

Deque のサイズになるまで、deque の末尾に近い要素が削除された deque のサイズが要求されたサイズより大きい場合は、 *_Newsize*します。

deque の現在のサイズが要求されたサイズと同じ場合は、何も実行されません。

[size](#size) は deque の現在のサイズを反映します。

### <a name="example"></a>例

```cpp
// deque_resize.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;

   c1.push_back( 10 );
   c1.push_back( 20 );
   c1.push_back( 30 );

   c1.resize( 4,40 );
   cout << "The size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is " << c1.back( ) << endl;

   c1.resize( 5 );
   cout << "The size of c1 is now: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;

   c1.resize( 2 );
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;
   cout << "The value of the last element is now " << c1.back( ) << endl;
}
```

```Output
The size of c1 is: 4
The value of the last element is 40
The size of c1 is now: 5
The value of the last element is now 0
The reduced size of c1 is: 2
The value of the last element is now 20
```

## <a name="reverse_iterator"></a>  deque::reverse_iterator

反転された deque 内の要素の読み取りまたは変更が可能なランダム アクセス反復子を提供する型。

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Remarks

`reverse_iterator` 型は、deque を反復処理するために使われます。

### <a name="example"></a>例

rbegin の例を参照してください。

## <a name="shrink_to_fit"></a>  deque::shrink_to_fit

余分なキャパシティを破棄します。

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Remarks

`shrink_to_fit` が [deque](../standard-library/deque-class.md) によって使われるストレージを削減するかどうかを特定するポータブルな方法はありません。

### <a name="example"></a>例

```cpp
// deque_shrink_to_fit.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> v1;
   //deque <int>::iterator Iter;

   v1.push_back( 1 );
   v1.push_back( 2 );
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
   v1.shrink_to_fit();
   cout << "Current size of v1 = "
      << v1.size( ) << endl;
}
```

```Output
Current size of v1 = 1
Current size of v1 = 1
```

## <a name="size"></a>  deque::size

deque 内の要素の数を返します。

```cpp
size_type size() const;
```

### <a name="return-value"></a>戻り値

deque の現在の長さ。

### <a name="example"></a>例

```cpp
// deque_size.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1;
   deque <int>::size_type i;

   c1.push_back( 1 );
   i = c1.size( );
   cout << "The deque length is " << i << "." << endl;

   c1.push_back( 2 );
   i = c1.size( );
   cout << "The deque length is now " << i << "." << endl;
}
```

```Output
The deque length is 1.
The deque length is now 2.
```

## <a name="size_type"></a>  deque::size_type

deque 内の要素の数をカウントする型。

```cpp
typedef typename Allocator::size_type size_type;
```

### <a name="example"></a>例

[size](#size) の例を参照してください。

## <a name="swap"></a>  deque::swap

2 つの deque の要素を交換します。

```cpp
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
交換する要素を提供する deque (deque `left` と要素を交換する deque)。

*left*<br/>
要素が deque のものと交換される deque*右*します。

### <a name="example"></a>例

```cpp
// deque_swap.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2, c3;
   deque <int>::iterator c1_Iter;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 3 );
   c2.push_back( 10 );
   c2.push_back( 20 );
   c3.push_back( 100 );

   cout << "The original deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   c1.swap( c2 );

   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap( c1,c3 );

   cout << "After swapping with c3, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;

   swap<>(c1, c2);
   cout << "After swapping with c2, deque c1 is:";
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )
      cout << " " << *c1_Iter;
   cout << endl;
}
```

```Output
The original deque c1 is: 1 2 3
After swapping with c2, deque c1 is: 10 20
After swapping with c3, deque c1 is: 100
After swapping with c2, deque c1 is: 1 2 3
```

## <a name="value_type"></a>  deque::value_type

deque 内に格納されているデータ型を表す型。

```cpp
typedef typename Allocator::value_type value_type;
```

### <a name="remarks"></a>Remarks

`value_type` はテンプレート パラメーター `Type` のシノニムです。

### <a name="example"></a>例

```cpp
// deque_value_type.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>
int main( )
{
   using namespace std;
   deque<int>::value_type AnInt;
   AnInt = 44;
   cout << AnInt << endl;
}
```

```Output
44
```

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
