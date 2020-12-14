---
description: 詳細については、「hash_set (STL/CLR)」を参照してください。
title: hash_set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::hash_set
- cliext::hash_set::begin
- cliext::hash_set::bucket_count
- cliext::hash_set::clear
- cliext::hash_set::const_iterator
- cliext::hash_set::const_reference
- cliext::hash_set::const_reverse_iterator
- cliext::hash_set::count
- cliext::hash_set::difference_type
- cliext::hash_set::empty
- cliext::hash_set::end
- cliext::hash_set::equal_range
- cliext::hash_set::erase
- cliext::hash_set::find
- cliext::hash_set::generic_container
- cliext::hash_set::generic_iterator
- cliext::hash_set::generic_reverse_iterator
- cliext::hash_set::generic_value
- cliext::hash_set::hash_delegate
- cliext::hash_set::hash_set
- cliext::hash_set::hasher
- cliext::hash_set::insert
- cliext::hash_set::iterator
- cliext::hash_set::key_comp
- cliext::hash_set::key_compare
- cliext::hash_set::key_type
- cliext::hash_set::load_factor
- cliext::hash_set::lower_bound
- cliext::hash_set::make_value
- cliext::hash_set::max_load_factor
- cliext::hash_set::operator=
- cliext::hash_set::rbegin
- cliext::hash_set::reference
- cliext::hash_set::rehash
- cliext::hash_set::rend
- cliext::hash_set::reverse_iterator
- cliext::hash_set::size
- cliext::hash_set::size_type
- cliext::hash_set::swap
- cliext::hash_set::to_array
- cliext::hash_set::upper_bound
- cliext::hash_set::value_comp
- cliext::hash_set::value_compare
- cliext::hash_set::value_type
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_set class [STL/CLR]
- <hash_set> header [STL/CLR]
- begin member [STL/CLR]
- bucket_count member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- hash_delegate member [STL/CLR]
- hash_set member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rehash member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
ms.openlocfilehash: 0705dd674af21958b5d4f4b0a5a904eb42aff76a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335474"
---
# <a name="hash_set-stlclr"></a>hash_set (STL/CLR)

このテンプレートクラスは、双方向アクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナーを使用し `hash_set` て、一連の要素をハッシュテーブルとして管理します。各テーブルエントリは、ノードの双方向のリンクリストを格納し、各ノードには1つの要素を格納します。 各要素の値は、シーケンスの順序付けのためにキーとして使用されます。

以下の説明で `GValue` は、はと同じですが、 `GKey` 後者が参照型である場合を除いて、 *キー* と同じです。この場合、は `Key^` です。

## <a name="syntax"></a>構文

```cpp
template<typename Key>
    ref class hash_set
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*キー*<br/>
被制御シーケンス内の要素のキー コンポーネントの型。

## <a name="requirements"></a>要件

**ヘッダー:**\<cliext/hash_set>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型の定義|説明|
|---------------------|-----------------|
|[hash_set::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[hash_set::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[hash_set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[hash_set::difference_type (STL/CLR)](#difference_type)|2つの要素間の (符号付きの) 距離の型。|
|[hash_set::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリックインターフェイスの型。|
|[hash_set::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリックインターフェイスの反復子の型。|
|[hash_set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリックインターフェイスの反転反復子の型。|
|[hash_set::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリックインターフェイスの要素の型。|
|[hash_set::hasher (STL/CLR)](#hasher)|キーのハッシュデリゲート。|
|[hash_set::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[hash_set::key_compare (STL/CLR)](#key_compare)|2つのキーの順序付けデリゲート。|
|[hash_set::key_type (STL/CLR)](#key_type)|順序付けキーの型です。|
|[hash_set::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[hash_set::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[hash_set::size_type (STL/CLR)](#size_type)|2つの要素間の (負ではない) 距離の型。|
|[hash_set::value_compare (STL/CLR)](#value_compare)|2つの要素の値の順序付けデリゲート。|
|[hash_set::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[hash_set::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[hash_set::bucket_count (STL/CLR)](#bucket_count)|バケット数をカウントします。|
|[hash_set::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[hash_set::count (STL/CLR)](#count)|指定されたキーに一致する要素をカウントします。|
|[hash_set::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[hash_set::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[hash_set::equal_range (STL/CLR)](#equal_range)|指定したキーに一致する範囲を検索します。|
|[hash_set::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[hash_set::find (STL/CLR)](#find)|指定したキーに一致する要素を検索します。|
|[hash_set::hash_delegate (STL/CLR)](#hash_delegate)|キーのハッシュデリゲートをコピーします。|
|[hash_set::hash_set (STL/CLR)](#hash_set)|コンテナー オブジェクトを構築します。|
|[hash_set::insert (STL/CLR)](#insert)|要素を追加します。|
|[hash_set::key_comp (STL/CLR)](#key_comp)|2つのキーの順序付けデリゲートをコピーします。|
|[hash_set::load_factor (STL/CLR)](#load_factor)|バケットごとの平均要素数をカウントします。|
|[hash_set::lower_bound (STL/CLR)](#lower_bound)|指定されたキーに一致する範囲の先頭を検索します。|
|[hash_set::make_value (STL/CLR)](#make_value)|値オブジェクトを構築します。|
|[hash_set::max_load_factor (STL/CLR)](#max_load_factor)|バケットあたりの最大要素数を取得または設定します。|
|[hash_set::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[hash_set::rehash (STL/CLR)](#rehash)|ハッシュ テーブルをリビルドします。|
|[hash_set::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[hash_set::size (STL/CLR)](#size)|要素の数をカウントします。|
|[hash_set::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[hash_set::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|
|[hash_set::upper_bound (STL/CLR)](#upper_bound)|指定されたキーに一致する範囲の末尾を検索します。|
|[hash_set::value_comp (STL/CLR)](#value_comp)|2つの要素の値の順序付けデリゲートをコピーします。|

|演算子|説明|
|--------------|-----------------|
|[hash_set::operator= (STL/CLR)](#op)|被制御シーケンスを置き換えます。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|<xref:System.Collections.IEnumerable>|要素を順番に処理します。|
|<xref:System.Collections.ICollection>|要素のグループを維持します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番に処理します。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|
|IHash\<Key, Value>|ジェネリックコンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、双方向のリンクリスト内の個々のノードとして制御するシーケンスのストレージを割り当て、解放します。 オブジェクトは、アクセスを高速化するために、リスト内のさまざまな長さのポインター (ハッシュテーブル) を維持し、一覧全体をサブリストまたはバケットのシーケンスとして効果的に管理します。 要素は、ノード間のリンクを変更することによって順序を維持するバケットに挿入されます。つまり、あるノードのコンテンツを別のノードにコピーすることはできません。 つまり、要素を自由に挿入および削除できます。

オブジェクトは、hash_set:: key_compare 型の格納されたデリゲートオブジェクトを呼び出すことによって制御する各バケットを並べ替えます [(STL/CLR)](#key_compare)。 Hash_set を構築するときに、格納されているデリゲートオブジェクトを指定できます。デリゲートオブジェクトを指定しない場合、既定では比較が行われ `operator<=(key_type, key_type)` ます。

格納されているデリゲートオブジェクトにアクセスするには、メンバー関数[hash_set:: key_comp (STL/CLR)](#key_comp)を呼び出し `()` ます。 このようなデリゲートオブジェクトでは、hash_set:: key_type 型のキー間の等価な順序を定義する必要があります [(STL/CLR)](#key_type)。 つまり、任意の2つのキーについては、次のようになり `X` `Y` ます。

`key_comp()(X, Y)` すべての呼び出しで同じブール型の結果を返します。

`key_comp()(X, Y) && key_comp()(Y, X)`が true の場合、 `X` と `Y` は等価の順序付けと呼ばれます。

のように動作する任意の順序付け規則 `operator<=(key_type, key_type)` `operator>=(key_type, key_type)` 。または、 `operator==(key_type, key_type)` eqivalent の順序を定義します。

コンテナーは、キーが同等の順序付け (および同じ整数値へのハッシュ) を持つ要素のみがバケット内で隣接していることを確認します。 テンプレートクラス [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)とは異なり、テンプレートクラスのオブジェクトは、 `hash_set` すべての要素のキーが一意であることを保証します。 (2 つのキーの順序が同じではありません)。

オブジェクトは、 [hash_set:: hasher (STL/CLR)](#hasher)型の格納されたデリゲートオブジェクトを呼び出すことによって、指定された順序付けキーを格納するバケットを決定します。 この格納されたオブジェクトにアクセスするには、メンバー関数[hash_set:: hash_delegate (STL/CLR)](#hash_delegate)を呼び出して、 `()` キー値に依存する整数値を取得します。 Hash_set を構築するときに、格納されているデリゲートオブジェクトを指定できます。delegate オブジェクトを指定しない場合、既定値は関数 `System::Object::hash_value(key_type)` です。 つまり、任意のキー `X` と `Y` :

`hash_delegate()(X)` すべての呼び出しで同じ整数の結果を返します。

`X`と `Y` の順序が等価である場合、 `hash_delegate()(X)` はと同じ整数の結果を返す必要があり `hash_delegate()(Y)` ます。

各要素は、キーと値の両方として機能します。 シーケンスは、シーケンス内の要素数に依存しない複数の操作 (定数時間) を使用して、任意の要素の検索、挿入、および削除を許可する方法で表現されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。

ただし、ハッシュされた値が一様に分布していない場合は、ハッシュテーブルが逆になることがあります。 極端なでは、常に同じ値を返すハッシュ関数の場合、lookup、挿入、および削除は、シーケンス内の要素数に比例します (線形時間)。 コンテナーは適切なハッシュ関数を選択します。バケットのサイズとハッシュテーブルのサイズ (バケットの合計数) を選択しますが、これらのオプションのいずれかまたはすべてを上書きすることができます。 たとえば、関数 [hash_set:: max_load_factor (stl/clr)](#max_load_factor) と [hash_set:: rehash (stl/clr)](#rehash)を参照してください。

Hash_set は双方向反復子をサポートします。これは、被制御シーケンス内の要素を指定する反復子が指定されている場合に隣接する要素にステップインできることを意味します。 特別なヘッドノードは[hash_set:: end (STL/CLR)](#end)によって返される反復子に対応 `()` します。 この反復子をデクリメントして、被制御シーケンスの最後の要素 (存在する場合) に移動することができます。 Hash_set 反復子をインクリメントしてヘッドノードに移動することができ、これはと等しいと比較され `end()` ます。 ただし、によって返される反復子を逆参照することはできません `end()` 。

ランダムアクセス反復子を必要とする数値の位置を指定して、hash_set 要素を直接参照することはできないことに注意してください。

Hash_set 反復子は、関連付けられている hash_set ノードへのハンドルを格納します。このハンドルは、関連付けられているコンテナーへのハンドルを格納します。 反復子は、関連付けられているコンテナーオブジェクトと共にのみ使用できます。 関連する hash_set ノードが hash_set に関連付けられている限り、hash_set 反復子は有効なままです。 さらに、有効な反復子は dereferencable です。これを使用すると、に指定した要素の値にアクセスしたり、変更したりすることができ `end()` ます。

要素を消去または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナーを破棄すると、すべての要素が消去されます。 したがって、要素の型が ref クラスであるコンテナーは、コンテナーの直後要素が存在しないことを保証します。 ただし、ハンドルのコンテナーが要素を破棄し *ない* ことに注意してください。

## <a name="members"></a>メンバー

## <a name="hash_setbegin-stlclr"></a><a name="begin"></a> hash_set:: begin (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素、または空のシーケンスの末尾の次の位置を指定する双方向反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_hash_set_begin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_set::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

## <a name="hash_setbucket_count-stlclr"></a><a name="bucket_count"></a> hash_set:: bucket_count (STL/CLR)

バケット数をカウントします。

### <a name="syntax"></a>構文

```cpp
int bucket_count();
```

### <a name="remarks"></a>解説

このメンバー関数は、現在のバケット数を返します。 これを使用して、ハッシュテーブルのサイズを決定します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setclear-stlclr"></a><a name="clear"></a> hash_set:: clear (STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

このメンバー関数は、実質的に[hash_set:: erase (stl](#erase) /clr) hash_set:: begin (stl/clr) `(` [](#begin) `(),` [hash_set:: end (stl/clr)](#end) `())` を呼び出します。 このメソッドを使用して、被制御シーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_clear.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="hash_setconst_iterator-stlclr"></a><a name="const_iterator"></a> hash_set:: const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T2` 被制御シーケンスの定数双方向反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_set::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setconst_reference-stlclr"></a><a name="const_reference"></a> hash_set:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_const_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_set::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_set::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> hash_set:: const_reverse_iterator (STL/CLR)

被制御シーケンスの定数反転反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T4` 被制御シーケンスの定数反転反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_set::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="hash_setcount-stlclr"></a><a name="count"></a> hash_set:: count (STL/CLR)

指定したキーに一致する要素の数を検索します。

### <a name="syntax"></a>構文

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、 *キー* と同じ順序付けを持つ被制御シーケンス内の要素の数を返します。 被制御シーケンス内の指定したキーに一致する現在の要素の数を確認する場合に、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="hash_setdifference_type-stlclr"></a><a name="difference_type"></a> hash_set::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、要素の数が負の値になる可能性があることを示します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_difference_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_set::difference_type diff = 0;
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_set::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="hash_setempty-stlclr"></a><a name="empty"></a> hash_set:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[hash_set:: size (STL/CLR)](#size)に相当 `() == 0` します。 Hash_set が空であるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_empty.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="hash_setend-stlclr"></a><a name="end"></a> hash_set:: end (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾の次の位置を指し示す双方向反復子を返します。 このメソッドを使用して、被制御シーケンスの末尾を指定する反復子を取得します。被制御シーケンスの長さが変更されている場合、その状態は変わりません。

### <a name="example"></a>例

```cpp
// cliext_hash_set_end.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_set::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="hash_setequal_range-stlclr"></a><a name="equal_range"></a> hash_set:: equal_range (STL/CLR)

指定したキーに一致する範囲を検索します。

### <a name="syntax"></a>構文

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、 `cliext::pair<iterator, iterator>(` [hash_set:: lower_bound (stl/clr)](#lower_bound) `(key),` [hash_set:: upper_bound (stl/clr)](#upper_bound)という反復子のペアを `(key))` 返します。 このメソッドを使用して、被制御シーケンス内の指定したキーに一致する要素の範囲を特定します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_equal_range.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
typedef Myhash_set::pair_iter_iter Pairii;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="hash_seterase-stlclr"></a><a name="erase"></a> hash_set:: erase (STL/CLR)

指定した位置にある要素を削除します。

### <a name="syntax"></a>構文

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
消去する範囲の先頭。

*key*<br/>
消去するキー値。

*last*<br/>
消去する範囲の末尾。

*where*<br/>
消去する要素。

### <a name="remarks"></a>解説

最初のメンバー関数 *は、が* 指す被制御シーケンスの要素を削除し、削除された要素の後に残っている最初の要素を指定する反復子を返します。そのような要素が存在しない場合は [hash_set:: end (STL/CLR)](#end)を返し `()` ます。 このメソッドを使用して、1つの要素を削除します。

2番目のメンバー関数は、範囲 [,) 内の被制御シーケンスの要素を削除 `first` `last` し、削除された要素の後に残っている最初の要素を指定する反復子を返します。その `end()` ような要素が存在しない場合は、を返します。 これを使用して、0個以上の連続する要素を削除します。

3番目のメンバー関数は、キーの順序が同じ *キーを持つ* 被制御シーケンスの要素を削除し、削除された要素の数を返します。 これを使用して、指定されたキーに一致するすべての要素を削除およびカウントします。

各要素の消去では、被制御シーケンス内の要素数の対数に比例して時間がかかります。

### <a name="example"></a>例

```cpp
// cliext_hash_set_erase.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    Myhash_set::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="hash_setfind-stlclr"></a><a name="find"></a> hash_set:: find (STL/CLR)

指定したキーに一致する要素を検索します。

### <a name="syntax"></a>構文

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

被制御シーケンス内の少なくとも1つの要素の順序が同じである *場合、メンバー* 関数は、これらの要素のいずれかを指定する反復子を返します。それ以外の場合は、 [hash_set:: end (STL/CLR)](#end)が返さ `()` れます。 このメソッドを使用して、被制御シーケンス内で、指定したキーに一致する要素を検索します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_find.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="hash_setgeneric_container-stlclr"></a><a name="generic_container"></a> hash_set:: generic_container (STL/CLR)

コンテナーのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_generic_container.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="hash_setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> hash_set:: generic_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_iterator gcit = gc1->begin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> hash_set:: generic_reverse_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する逆順反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反転反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="hash_setgeneric_value-stlclr"></a><a name="generic_value"></a> hash_set:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、 `GValue` このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_generic_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_iterator gcit = gc1->begin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_sethash_delegate-stlclr"></a><a name="hash_delegate"></a> hash_set:: hash_delegate (STL/CLR)

指定したキーに一致する要素を検索します。

### <a name="syntax"></a>構文

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>解説

このメンバー関数は、キー値を整数に変換するために使用されるデリゲートを返します。 キーをハッシュするために使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_sethash_set-stlclr"></a><a name="hash_set"></a> hash_set:: hash_set (STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
hash_set();
explicit hash_set(key_compare^ pred);
hash_set(key_compare^ pred, hasher^ hashfn);
hash_set(hash_set<Key>% right);
hash_set(hash_set<Key>^ right);
template<typename InIter>
    hash_sethash_set(InIter first, InIter last);
template<typename InIter>
    hash_set(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_set(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
挿入する範囲の先頭。

*hashfn*<br/>
キーをバケットにマッピングするためのハッシュ関数。

*last*<br/>
挿入する範囲の末尾。

*pred*<br/>
被制御シーケンスの順序付け述語。

*そうです*<br/>
挿入するオブジェクトまたは範囲。

### <a name="remarks"></a>解説

コンストラクター:

`hash_set();`

既定の順序述語と既定のハッシュ関数を使用して、要素なしで被制御シーケンスを初期化し `key_compare()` ます。 既定の順序述語とハッシュ関数を使用して、空の初期被制御シーケンスを指定するために使用します。

コンストラクター:

`explicit hash_set(key_compare^ pred);`

順序述語 *pred*、および既定のハッシュ関数を使用して、要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、指定した順序述語と既定のハッシュ関数を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`hash_set(key_compare^ pred, hasher^ hashfn);`

順序述語 *pred* とハッシュ関数 *hashfn* を使用して、要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、指定された順序述語とハッシュ関数を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`hash_set(hash_set<Key>% right);`

`right.begin()`既定の順序述語と既定のハッシュ関数を使用して、シーケンス [,) を使用して被制御シーケンスを初期化し `right.end()` ます。 これを使用して、hash_set オブジェクト *権限* によって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`hash_set(hash_set<Key>^ right);`

`right->begin()`既定の順序述語と既定のハッシュ関数を使用して、シーケンス [,) を使用して被制御シーケンスを初期化し `right->end()` ます。 これを使用して、hash_set オブジェクト *権限* によって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`template<typename InIter> hash_set(InIter first, InIter last);`

`first`既定の順序述語と既定のハッシュ関数を使用して、シーケンス [,) を使用して被制御シーケンスを初期化し `last` ます。 このメソッドを使用して、被制御シーケンスを別のシーケンスのコピーにし、既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred);`

順序 `first` `last` 述語 *pred* を使用し、既定のハッシュ関数を使用して、シーケンス [,) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、指定された順序述語と既定のハッシュ関数を使用して、被制御シーケンスを別のシーケンスのコピーにします。

コンストラクター:

`template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

順序 `first` `last` 述語 *pred* を使用し、ハッシュ関数 *hashfn* を使用して、被制御シーケンスをシーケンス [,) で初期化します。 このメソッドを使用して、被制御シーケンスに別のシーケンスのコピーを指定し、順序付け述語とハッシュ関数を指定します。

コンストラクター:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`

列挙子 *権限* によって指定されたシーケンス、既定の順序述語、および既定のハッシュ関数を使用して、被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、列挙子によって記述された別のシーケンスのコピーにし、既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

列挙述語 *pred* を使用し、既定のハッシュ関数を使用して、列挙子の *権限* で指定されたシーケンスを使用して、被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、指定した順序述語と既定のハッシュ関数を使用して、列挙子によって記述された別のシーケンスのコピーにします。

コンストラクター:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

順序付け述語 *pred* を使用し、ハッシュ関数 *hashfn* を使用して、列挙子 *権限* によって指定されたシーケンスを使用して被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、列挙述語とハッシュ関数を指定して、列挙子によって記述された別のシーケンスのコピーにします。

### <a name="example"></a>例

```cpp
// cliext_hash_set_construct.cpp
// compile with: /clr
#include <cliext/hash_set>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
// construct an empty container
    Myhash_set c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_set c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_set::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_set c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_set c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_set c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_set::hasher(&myfun));
    for each (wchar_t elem in c4h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_set c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_set c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_set c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>(),
                gcnew Myhash_set::hasher(&myfun));
    for each (wchar_t elem in c6h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct from a generic container
    Myhash_set c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_set c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
a b c
size() = 0
c b a

a b c
a b c
c b a

a b c
a b c
c b a

a b c
a b c
```

## <a name="hash_sethasher-stlclr"></a><a name="hasher"></a> hash_set:: hasher (STL/CLR)

キーのハッシュデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>解説

この型は、キー値を整数に変換するデリゲートを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_hasher.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_setinsert-stlclr"></a><a name="insert"></a> hash_set:: insert (STL/CLR)

要素を追加します。

### <a name="syntax"></a>構文

```cpp
cliext::pair<iterator, bool> insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*そうです*<br/>
挿入する列挙体。

*val*<br/>
挿入するキー値。

*where*<br/>
コンテナー内の挿入位置 (ヒントのみ)。

### <a name="remarks"></a>解説

各メンバー関数は、残りのオペランドによって指定されたシーケンスを挿入します。

1つ目のメンバー関数は、値 *val* を持つ要素を挿入し、値のペアを返し `X` ます。 が true の場合は `X.second` 、新しく挿入された要素を指定し `X.first` ます。それ以外の場合は、 `X.first` 既に存在し、新しい要素が挿入されない、同じ順序の要素を指定します。 1つの要素を挿入するために使用します。

2番目のメンバー関数は、(パフォーマンスを向上させるために) ヒントと *してを使用し* て、値 *val* を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 これを使用して、既知の要素に隣接している可能性のある単一の要素を挿入します。

3番目のメンバー関数は、シーケンス [,) を挿入し `first` `last` ます。 このメソッドを使用して、別のシーケンスからコピーされた0個以上の要素を挿入します。

4番目のメンバー関数は、 *右側* に指定されたシーケンスを挿入します。 このメソッドを使用して、列挙子によって記述されたシーケンスを挿入します。

各要素の挿入には、被制御シーケンス内の要素数の対数に比例した時間がかかります。 挿入ポイントに隣接する要素を指定するヒントを指定すると、挿入は償却定数時間で実行できます。

### <a name="example"></a>例

```cpp
// cliext_hash_set_insert.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
typedef Myhash_set::pair_iter_bool Pairib;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_set c2;
    Myhash_set::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_set c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="hash_setiterator-stlclr"></a><a name="iterator"></a> hash_set:: iterator (STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、 `T1` 被制御シーケンスの双方向反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_set::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setkey_comp-stlclr"></a><a name="key_comp"></a> hash_set:: key_comp (STL/CLR)

2つのキーの順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 2 つのキーを比較する場合にこれを使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_key_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_set c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_setkey_compare-stlclr"></a><a name="key_compare"></a> hash_set:: key_compare (STL/CLR)

2つのキーの順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>解説

この型は、キー引数の順序を決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_hash_set_key_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_set c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_setkey_type-stlclr"></a><a name="key_type"></a> hash_set:: key_type (STL/CLR)

順序付けキーの型です。

### <a name="syntax"></a>構文

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター *キー* のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_hash_set_key_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_set::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setload_factor-stlclr"></a><a name="load_factor"></a> hash_set:: load_factor (STL/CLR)

バケットごとの平均要素数をカウントします。

### <a name="syntax"></a>構文

```cpp
float load_factor();
```

### <a name="remarks"></a>解説

このメンバー関数は、 `(float)` [hash_set:: size (stl/clr)](#size) `() /` [hash_set:: bucket_count (stl/clr)](#bucket_count)を返し `()` ます。 この値を使用して、バケットの平均サイズを決定します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setlower_bound-stlclr"></a><a name="lower_bound"></a> hash_set:: lower_bound (STL/CLR)

指定されたキーに一致する範囲の先頭を検索します。

### <a name="syntax"></a>構文

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、 `X` *キー* と同じバケットにハッシュし、 *キー* と同等の順序を持つ被制御シーケンス内の最初の要素を決定します。 そのような要素が存在しない場合は[hash_set:: end (STL/CLR)](#end)を返します。それ以外の場合はを `()` 指定する反復子を返し `X` ます。 このメソッドを使用して、被制御シーケンスの中で、指定したキーに一致する要素のシーケンスの先頭を検索します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="hash_setmake_value-stlclr"></a><a name="make_value"></a> hash_set:: make_value (STL/CLR)

値オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
使用するキー値。

### <a name="remarks"></a>解説

このメンバー関数は、キー `value_type` が *key* であるオブジェクトを返します。 これを使用して、他のいくつかのメンバー関数との使用に適したオブジェクトを作成します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_make_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(Myhash_set::make_value(L'a'));
    c1.insert(Myhash_set::make_value(L'b'));
    c1.insert(Myhash_set::make_value(L'c'));

    // display contents " a b c"
    for each (Myhash_set::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setmax_load_factor-stlclr"></a><a name="max_load_factor"></a> hash_set:: max_load_factor (STL/CLR)

バケットあたりの最大要素数を取得または設定します。

### <a name="syntax"></a>構文

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>パラメーター

*new_factor*<br/>
格納する新しい最大負荷係数。

### <a name="remarks"></a>解説

最初のメンバー関数は、現在格納されている最大テーブル占有率を返します。 この値を使用して、バケットの最大サイズを決定します。

2番目のメンバー関数は、ストアの最大占有率を *new_factor* に置き換えます。 後続の挿入まで自動悪くは発生しません。

### <a name="example"></a>例

```cpp
// cliext_hash_set_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

## <a name="hash_setoperator-stlclr"></a><a name="op"></a> hash_set:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
hash_set<Key>% operator=(hash_set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに *right* をコピーし、を返し **`*this`** ます。 このメソッドを使用して、被制御シーケンスを *右側* の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_hash_set_operator_as.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Myhash_set::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_set c2;
    c2 = c1;
// display contents " a b c"
    for each (Myhash_set::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="hash_setrbegin-stlclr"></a><a name="rbegin"></a> hash_set:: rbegin (STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素、または空のシーケンスの先頭の次の位置を指定する反転反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_hash_set_rbegin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_set::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="hash_setreference-stlclr"></a><a name="reference"></a> hash_set:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_set::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_set::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setrehash-stlclr"></a><a name="rehash"></a> hash_set:: rehash (STL/CLR)

ハッシュ テーブルをリビルドします。

### <a name="syntax"></a>構文

```cpp
void rehash();
```

### <a name="remarks"></a>解説

このメンバー関数は、 [hash_set:: load_factor (stl/clr)](#load_factor) `() <=` [hash_set:: max_load_factor (stl/clr)](#max_load_factor)が確実になるように、ハッシュテーブルを再構築します。 それ以外の場合、ハッシュテーブルのサイズは、挿入後の必要に応じて大きくなります。 (サイズが自動的に縮小されることはありません)。ハッシュテーブルのサイズを調整するには、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_rehash.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setrend-stlclr"></a><a name="rend"></a> hash_set:: rend (STL/CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの先頭を越えた位置を示す反転反復子を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_hash_set_rend.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_set::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="hash_setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> hash_set:: reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T3` 被制御シーケンスの反転反復子として使用できる指定されていない型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_set::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="hash_setsize-stlclr"></a><a name="size"></a> hash_set:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスにゼロ以外のサイズがあるかどうかについては、「 [hash_set:: empty (STL/CLR)](#empty)」を参照してください `()` 。

### <a name="example"></a>例

```cpp
// cliext_hash_set_size.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="hash_setsize_type-stlclr"></a><a name="size_type"></a> hash_set:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_size_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_set::size_type diff = 0;
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="hash_setswap-stlclr"></a><a name="swap"></a> hash_set:: swap (STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(hash_set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

このメンバー関数は、との間で被制御シーケンスを交換し **`this`** ます。  この処理は一定時間に実行され、例外はスローされません。 2つのコンテナーの内容を簡単に交換する方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_swap.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_set c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
d e f
d e f
a b c
```

## <a name="hash_setto_array-stlclr"></a><a name="to_array"></a> hash_set:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_to_array.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="hash_setupper_bound-stlclr"></a><a name="upper_bound"></a> hash_set:: upper_bound (STL/CLR)

指定されたキーに一致する範囲の末尾を検索します。

### <a name="syntax"></a>構文

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、 `X` *キー* と同じバケットにハッシュし、 *キー* と同等の順序を持つ被制御シーケンスの最後の要素を決定します。 そのような要素が存在しない場合、またはが被制御シーケンスの最後の要素である場合は、 `X` [hash_set:: END (STL/CLR)](#end)を返します。それ以外の場合は、 `()` 最初の要素を指定する反復子を返し `X` ます。 このメソッドを使用して、被制御シーケンスの中で、指定したキーに一致する要素のシーケンスの末尾を検索します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="hash_setvalue_comp-stlclr"></a><a name="value_comp"></a> hash_set:: value_comp (STL/CLR)

2つの要素の値の順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 これを使用して、2つの要素の値を比較します。

### <a name="example"></a>例

```cpp
// cliext_hash_set_value_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="hash_setvalue_compare-stlclr"></a><a name="value_compare"></a> hash_set:: value_compare (STL/CLR)

2つの要素の値の順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>解説

この型は、値引数の順序を決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_hash_set_value_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="hash_setvalue_type-stlclr"></a><a name="value_type"></a> hash_set:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>解説

この型は `generic_value` の同意語です。

### <a name="example"></a>例

```cpp
// cliext_hash_set_value_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_set::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```
