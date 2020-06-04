---
title: hash_multimap (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::hash_multimap
- cliext::hash_multimap::begin
- cliext::hash_multimap::bucket_count
- cliext::hash_multimap::clear
- cliext::hash_multimap::const_iterator
- cliext::hash_multimap::const_reference
- cliext::hash_multimap::const_reverse_iterator
- cliext::hash_multimap::count
- cliext::hash_multimap::difference_type
- cliext::hash_multimap::empty
- cliext::hash_multimap::end
- cliext::hash_multimap::equal_range
- cliext::hash_multimap::erase
- cliext::hash_multimap::find
- cliext::hash_multimap::generic_container
- cliext::hash_multimap::generic_iterator
- cliext::hash_multimap::generic_reverse_iterator
- cliext::hash_multimap::generic_value
- cliext::hash_multimap::hash_delegate
- cliext::hash_multimap::hash_multimap
- cliext::hash_multimap::hasher
- cliext::hash_multimap::insert
- cliext::hash_multimap::iterator
- cliext::hash_multimap::key_comp
- cliext::hash_multimap::key_compare
- cliext::hash_multimap::key_type
- cliext::hash_multimap::load_factor
- cliext::hash_multimap::lower_bound
- cliext::hash_multimap::make_value
- cliext::hash_multimap::mapped_type
- cliext::hash_multimap::max_load_factor
- cliext::hash_multimap::operator=
- cliext::hash_multimap::rbegin
- cliext::hash_multimap::reference
- cliext::hash_multimap::rehash
- cliext::hash_multimap::rend
- cliext::hash_multimap::reverse_iterator
- cliext::hash_multimap::size
- cliext::hash_multimap::size_type
- cliext::hash_multimap::swap
- cliext::hash_multimap::to_array
- cliext::hash_multimap::upper_bound
- cliext::hash_multimap::value_comp
- cliext::hash_multimap::value_compare
- cliext::hash_multimap::value_type
helpviewer_keywords:
- hash_multimap class [STL/CLR]
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
- begin member [STL/CLR]
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
- hash_multimap member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- mapped_type member [STL/CLR]
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
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
ms.openlocfilehash: 815ec8c51bf4a446d5ff92c443f1086c1b2d0eca
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208716"
---
# <a name="hash_multimap-stlclr"></a>hash_multimap (STL/CLR)

このテンプレートクラスは、双方向アクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナー `hash_multimap` は、一連の要素をハッシュテーブルとして管理するために使用します。各テーブルエントリは、ノードの双方向のリンクリストを格納し、各ノードには1つの要素を格納します。 要素は、シーケンスを順序付けるためのキーと、その乗り物に沿ってマップされる値で構成されます。

以下の説明では、`GValue` は次のようになります。

`Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`

各値の説明:

`GKey` は、後者が参照型である場合を除き、*キー*と同じです。この場合は、`Key^`

`GMapped` は、後者が参照型である場合を除き、*マップ*と同じです。この場合は、`Mapped^`

## <a name="syntax"></a>構文

```cpp
template<typename Key,
    typename Mapped>
    ref class hash_multimap
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

*[キー]*<br/>
被制御シーケンス内の要素のキー コンポーネントの型。

*付け*<br/>
被制御シーケンス内の要素の追加コンポーネントの型。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<cliext/hash_map >

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型定義|説明|
|---------------------|-----------------|
|[hash_multimap::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[hash_multimap::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[hash_multimap::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[hash_multimap::difference_type (STL/CLR)](#difference_type)|2つの要素間の (符号付きの) 距離の型。|
|[hash_multimap::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリックインターフェイスの型。|
|[hash_multimap::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリックインターフェイスの反復子の型。|
|[hash_multimap::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリックインターフェイスの反転反復子の型。|
|[hash_multimap::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリックインターフェイスの要素の型。|
|[hash_multimap::hasher (STL/CLR)](#hasher)|キーのハッシュデリゲート。|
|[hash_multimap::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[hash_multimap::key_compare (STL/CLR)](#key_compare)|2つのキーの順序付けデリゲート。|
|[hash_multimap::key_type (STL/CLR)](#key_type)|順序付けキーの型です。|
|[hash_multimap::mapped_type (STL/CLR)](#mapped_type)|各キーに関連付けられているマップ値の型。|
|[hash_multimap::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[hash_multimap::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[hash_multimap::size_type (STL/CLR)](#size_type)|2つの要素間の (負ではない) 距離の型。|
|[hash_multimap::value_compare (STL/CLR)](#value_compare)|2つの要素の値の順序付けデリゲート。|
|[hash_multimap::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[hash_multimap::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[hash_multimap::bucket_count (STL/CLR)](#bucket_count)|バケット数をカウントします。|
|[hash_multimap::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[hash_multimap::count (STL/CLR)](#count)|指定されたキーに一致する要素をカウントします。|
|[hash_multimap::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[hash_multimap::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[hash_multimap::equal_range (STL/CLR)](#equal_range)|指定したキーに一致する範囲を検索します。|
|[hash_multimap::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[hash_multimap::find (STL/CLR)](#find)|指定したキーに一致する要素を検索します。|
|[hash_multimap::hash_delegate (STL/CLR)](#hash_delegate)|キーのハッシュデリゲートをコピーします。|
|[hash_multimap::hash_multimap (STL/CLR)](#hash_multimap)|コンテナー オブジェクトを構築します。|
|[hash_multimap::insert (STL/CLR)](#insert)|要素を追加します。|
|[hash_multimap::key_comp (STL/CLR)](#key_comp)|2つのキーの順序付けデリゲートをコピーします。|
|[hash_multimap::load_factor (STL/CLR)](#load_factor)|バケットごとの平均要素数をカウントします。|
|[hash_multimap::lower_bound (STL/CLR)](#lower_bound)|指定されたキーに一致する範囲の先頭を検索します。|
|[hash_multimap::make_value (STL/CLR)](#make_value)|値オブジェクトを構築します。|
|[hash_multimap::max_load_factor (STL/CLR)](#max_load_factor)|バケットあたりの最大要素数を取得または設定します。|
|[hash_multimap::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[hash_multimap::rehash (STL/CLR)](#rehash)|ハッシュ テーブルをリビルドします。|
|[hash_multimap::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[hash_multimap::size (STL/CLR)](#size)|要素の数をカウントします。|
|[hash_multimap::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[hash_multimap::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|
|[hash_multimap::upper_bound (STL/CLR)](#upper_bound)|指定されたキーに一致する範囲の末尾を検索します。|
|[hash_multimap::value_comp (STL/CLR)](#value_comp)|2つの要素の値の順序付けデリゲートをコピーします。|

|演算子|説明|
|--------------|-----------------|
|[hash_multimap::operator= (STL/CLR)](#op)|被制御シーケンスを置き換えます。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|<xref:System.Collections.IEnumerable>|要素を順番に処理します。|
|<xref:System.Collections.ICollection>|要素のグループを維持します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番に処理します。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|
|IHash\<キー、値 >|ジェネリックコンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、双方向のリンクリスト内の個々のノードとして制御するシーケンスのストレージを割り当て、解放します。 オブジェクトは、アクセスを高速化するために、リスト内のさまざまな長さのポインター (ハッシュテーブル) を維持し、一覧全体をサブリストまたはバケットのシーケンスとして効果的に管理します。 要素は、ノード間のリンクを変更することによって順序を維持するバケットに挿入されます。つまり、あるノードのコンテンツを別のノードにコピーすることはできません。 つまり、要素を自由に挿入および削除できます。

オブジェクトは、hash_set:: key_compare 型の格納されたデリゲートオブジェクトを呼び出すことによって制御する各バケットを並べ替えます[(STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)。 Hash_set を構築するときに、格納されているデリゲートオブジェクトを指定できます。delegate オブジェクトを指定しない場合、既定では `operator<=(key_type, key_type)`の比較が行われます。

格納されているデリゲートオブジェクトにアクセスするには、メンバー関数[hash_set:: key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`を呼び出します。 このようなデリゲートオブジェクトでは、hash_set:: key_type 型のキー間の等価な順序を定義する必要があります[(STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)。 つまり、`X` と `Y`の2つのキーについては、次のようになります。

`key_comp()(X, Y)` は、すべての呼び出しで同じブール値を返します。

`key_comp()(X, Y) && key_comp()(Y, X)` が true の場合、`X` と `Y` は等価の順序付けと呼ばれます。

`operator<=(key_type, key_type)`、`operator>=(key_type, key_type)` または `operator==(key_type, key_type)` のように動作する順序付け規則では、eqivalent の順序が定義されます。

コンテナーは、キーが同等の順序付け (および同じ整数値へのハッシュ) を持つ要素のみがバケット内で隣接していることを確認します。 テンプレートクラス[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)とは異なり、テンプレートクラス `hash_multimap` のオブジェクトでは、すべての要素のキーが一意である必要はありません。 (2 つ以上のキーが同等の順序を持つことができます)。

オブジェクトは、 [hash_set:: hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)型の格納されたデリゲートオブジェクトを呼び出すことによって、指定された順序付けキーを格納するバケットを決定します。 この格納されたオブジェクトにアクセスするには、メンバー関数[hash_set:: hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` を呼び出して、キー値に依存する整数値を取得します。 Hash_set を構築するときに、格納されているデリゲートオブジェクトを指定できます。delegate オブジェクトを指定しない場合、既定値は `System::Object::hash_value(key_type)`関数です。 つまり、`X` と `Y`のキーについては、次のようになります。

`hash_delegate()(X)` は、すべての呼び出しで同じ整数の結果を返します。

`X` と `Y` の順序が等価である場合、`hash_delegate()(X)` は `hash_delegate()(Y)`と同じ整数の結果を返す必要があります。

各要素には、個別のキーとマップされた値が含まれます。 シーケンスは、シーケンス内の要素数に依存しない複数の操作 (定数時間) を使用して、任意の要素の検索、挿入、および削除を許可する方法で表現されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。

ただし、ハッシュされた値が一様に分布していない場合は、ハッシュテーブルが逆になることがあります。 極端なでは、常に同じ値を返すハッシュ関数の場合、lookup、挿入、および削除は、シーケンス内の要素数に比例します (線形時間)。 コンテナーは適切なハッシュ関数を選択します。バケットのサイズとハッシュテーブルのサイズ (バケットの合計数) を選択しますが、これらのオプションのいずれかまたはすべてを上書きすることができます。 たとえば、関数[hash_set:: max_load_factor (stl/clr)](../dotnet/hash-set-max-load-factor-stl-clr.md)と[hash_set:: rehash (stl/clr)](../dotnet/hash-set-rehash-stl-clr.md)を参照してください。

Hash_multimap は双方向反復子をサポートします。これは、被制御シーケンス内の要素を指定する反復子が指定されている場合に隣接する要素にステップインできることを意味します。 特別なヘッドノードは[hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`によって返される反復子に対応します。 この反復子をデクリメントして、被制御シーケンスの最後の要素 (存在する場合) に移動することができます。 Hash_multimap 反復子をインクリメントしてヘッドノードに移動すると、`end()`と等しいかどうかが比較されます。 ただし、`end()`によって返される反復子を逆参照することはできません。

ランダムアクセス反復子を必要とする数値の位置を指定して、hash_multimap 要素を直接参照することはできないことに注意してください。

Hash_multimap 反復子は、関連付けられている hash_multimap ノードへのハンドルを格納します。このハンドルは、関連付けられているコンテナーへのハンドルを格納します。 反復子は、関連付けられているコンテナーオブジェクトと共にのみ使用できます。 関連する hash_multimap ノードが hash_multimap に関連付けられている限り、hash_multimap 反復子は有効なままです。 さらに、有効な反復子は dereferencable です。これを使用すると、指定した要素の値にアクセスしたり変更したりすることができます。これは、`end()`と等しくない場合に限ります。

要素を消去または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナーを破棄すると、すべての要素が消去されます。 したがって、要素の型が ref クラスであるコンテナーは、コンテナーの直後要素が存在しないことを保証します。 ただし、ハンドルのコンテナーが要素を破棄し*ない*ことに注意してください。

## <a name="members"></a>メンバー

## <a name="hash_multimapbegin-stlclr"></a><a name="begin"></a>hash_multimap:: begin (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素、または空のシーケンスの末尾の次の位置を指定する双方向反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_begin.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_multimap::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*++begin() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*begin() = [a 1]
*++begin() = [b 2]
```

## <a name="hash_multimapbucket_count-stlclr"></a><a name="bucket_count"></a>hash_multimap:: bucket_count (STL/CLR)

バケット数をカウントします。

### <a name="syntax"></a>構文

```cpp
int bucket_count();
```

### <a name="remarks"></a>解説

このメンバー関数は、現在のバケット数を返します。 これを使用して、ハッシュテーブルのサイズを決定します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="hash_multimapclear-stlclr"></a><a name="clear"></a>hash_multimap:: clear (STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

このメンバー関数は、実質的に[hash_multimap:: erase](../dotnet/hash-multimap-erase-stl-clr.md) (stl/clr)`(` [hash_multimap:: begin](../dotnet/hash-multimap-begin-stl-clr.md) (stl/clr)`(),` [HASH_MULTIMAP:: end (stl/](../dotnet/hash-multimap-end-stl-clr.md) clr)`())`を呼び出します。 このメソッドを使用して、被制御シーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_clear.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));

    // display contents " [a 1] [b 2]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2]
size() = 0
```

## <a name="hash_multimapconst_iterator-stlclr"></a><a name="const_iterator"></a>hash_multimap:: const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数双方向反復子として使用できる、未指定の型 `T2` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("[{0} {1}] ", cit->first, cit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapconst_reference-stlclr"></a><a name="const_reference"></a>hash_multimap:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_const_reference.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_multimap::const_reference cref = *cit;
        System::Console::Write("[{0} {1}] ", cref->first, cref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>hash_multimap:: const_reverse_iterator (STL/CLR)

被制御シーケンスの定数反転反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数反転反復子として使用できる、指定されていない型 `T4` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Myhash_multimap::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("[{0} {1}] ", crit->first, crit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="hash_multimapcount-stlclr"></a><a name="count"></a>hash_multimap:: count (STL/CLR)

指定したキーに一致する要素の数を検索します。

### <a name="syntax"></a>構文

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、*キー*と同じ順序付けを持つ被制御シーケンス内の要素の数を返します。 被制御シーケンス内の指定したキーに一致する現在の要素の数を確認する場合に、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_count.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="hash_multimapdifference_type-stlclr"></a><a name="difference_type"></a>hash_multimap::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、要素の数が負の値になる可能性があることを示します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_difference_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multimap::difference_type diff = 0;
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_multimap::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
begin()-end() = -3
```

## <a name="hash_multimapempty-stlclr"></a><a name="empty"></a>hash_multimap:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[hash_multimap:: size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md)`() == 0`と同じです。 Hash_multimap が空であるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_empty.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="hash_multimapend-stlclr"></a><a name="end"></a>hash_multimap:: end (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾の次の位置を指し示す双方向反復子を返します。 このメソッドを使用して、被制御シーケンスの末尾を指定する反復子を取得します。被制御シーケンスの長さが変更されている場合、その状態は変わりません。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_end.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_multimap::iterator it = c1.end();
    --it;
    --it;
    System::Console::WriteLine("*-- --end() = [{0} {1}]",
        it->first, it->second);
    ++it;
    System::Console::WriteLine("*--end() = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --end() = [b 2]
*--end() = [c 3]
```

## <a name="hash_multimapequal_range-stlclr"></a><a name="equal_range"></a>hash_multimap:: equal_range (STL/CLR)

指定したキーに一致する範囲を検索します。

### <a name="syntax"></a>構文

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、 [hash_multimap:: lower_bound (stl/clr)](../dotnet/hash-multimap-lower-bound-stl-clr.md)`(key),` [hash_multimap:: upper_bound (stl/clr)](../dotnet/hash-multimap-upper-bound-stl-clr.md)`(key))``cliext::pair<iterator, iterator>(` の反復子のペアを返します。 このメソッドを使用して、被制御シーケンス内の指定したキーに一致する要素の範囲を特定します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_equal_range.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
typedef Myhash_multimap::pair_iter_iter Pairii;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("[{0} {1}] ",
            pair1.first->first, pair1.first->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
equal_range(L'x') empty = True
[b 2]
```

## <a name="hash_multimaperase-stlclr"></a><a name="erase"></a>hash_multimap:: erase (STL/CLR)

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

最初のメンバー関数*は、が*指す被制御シーケンスの要素を削除し、削除された要素の後に残っている最初の要素を指定する反復子を返します。そのような要素が存在しない場合は[hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()` します。 このメソッドを使用して、1つの要素を削除します。

2番目のメンバー関数は、被制御シーケンスの要素を [`first`、`last`) の範囲で削除し、削除された要素の後に残っている最初の要素を指定する反復子を返します。そのような要素が存在しない場合は `end()` します。 これを使用して、0個以上の連続する要素を削除します。

3番目のメンバー関数は、キーの順序が同じ*キーを持つ*被制御シーケンスの要素を削除し、削除された要素の数を返します。 これを使用して、指定されたキーに一致するすべての要素を削除およびカウントします。

各要素の消去では、被制御シーケンス内の要素数の対数に比例して時間がかかります。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_erase.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    cliext::hash_multimap<wchar_t, int> c1;
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'a', 1));
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'b', 2));
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase an element and reinspect
    cliext::hash_multimap<wchar_t, int>::iterator it =
        c1.erase(c1.begin());
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",
        it->first, it->second);

    // add elements and display " b c d e"
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'd', 4));
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'e', 5));
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // erase all but end
    it = c1.end();
    it = c1.erase(c1.begin(), --it);
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",
        it->first, it->second);
    System::Console::WriteLine("size() = {0}", c1.size());

    // erase end
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
erase(begin()) = [b 2]
[b 2] [c 3] [d 4] [e 5]
erase(begin(), end()-1) = [e 5]
size() = 1
erase(L'x') = 0
erase(L'e') = 1
```

## <a name="hash_multimapfind-stlclr"></a><a name="find"></a>hash_multimap:: find (STL/CLR)

指定したキーに一致する要素を検索します。

### <a name="syntax"></a>構文

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

被制御シーケンス内の少なくとも1つの要素の順序が同じである*場合、メンバー*関数は、これらの要素のいずれかを指定する反復子を返します。それ以外の場合は、 [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`を返します。 このメソッドを使用して、被制御シーケンス内で、指定したキーに一致する要素を検索します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_find.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());

    Myhash_multimap::iterator it = c1.find(L'b');
    System::Console::WriteLine("find {0} = [{1} {2}]",
        L'b', it->first, it->second);

    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
find A = False
find b = [b 2]
find C = False
```

## <a name="hash_multimapgeneric_container-stlclr"></a><a name="generic_container"></a>hash_multimap:: generic_container (STL/CLR)

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
// cliext_hash_multimap_generic_container.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(Myhash_multimap::make_value(L'd', 4));
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(Myhash_multimap::make_value(L'e', 5));
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3] [d 4] [e 5]
```

## <a name="hash_multimapgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>hash_multimap:: generic_iterator (STL/CLR)

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
// cliext_hash_multimap_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multimap::generic_iterator gcit = gc1->begin();
    Myhash_multimap::generic_value gcval = *gcit;
    System::Console::Write("[{0} {1}] ", gcval->first, gcval->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="hash_multimapgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>hash_multimap:: generic_reverse_iterator (STL/CLR)

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
// cliext_hash_multimap_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multimap::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_multimap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3]
```

## <a name="hash_multimapgeneric_value-stlclr"></a><a name="generic_value"></a>hash_multimap:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する `GValue` 型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_generic_value.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_multimap::generic_container^ gc1 = %c1;
    for each (Myhash_multimap::value_type elem in gc1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_multimap::generic_iterator gcit = gc1->begin();
    Myhash_multimap::generic_value gcval = *gcit;
    System::Console::WriteLine("[{0} {1}] ", gcval->first, gcval->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[a 1]
```

## <a name="hash_multimaphash_delegate-stlclr"></a><a name="hash_delegate"></a>hash_multimap:: hash_delegate (STL/CLR)

指定したキーに一致する要素を検索します。

### <a name="syntax"></a>構文

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>解説

このメンバー関数は、キー値を整数に変換するために使用されるデリゲートを返します。 キーをハッシュするために使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_multimaphash_multimap-stlclr"></a><a name="hash_multimap"></a>hash_multimap:: hash_multimap (STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
hash_multimap();
explicit hash_multimap(key_compare^ pred);
hash_multimap(key_compare^ pred, hasher^ hashfn);
hash_multimap(hash_multimap<Key, Mapped>% right);
hash_multimap(hash_multimap<Key, Mapped>^ right);
template<typename InIter>
    hash_multimaphash_multimap(InIter first, InIter last);
template<typename InIter>
    hash_multimap(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_multimap(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,
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

*right*<br/>
挿入するオブジェクトまたは範囲。

### <a name="remarks"></a>解説

コンストラクター:

`hash_multimap();`

既定の順序述語 `key_compare()`、既定のハッシュ関数を使用して、要素を含まない被制御シーケンスを初期化します。 既定の順序述語とハッシュ関数を使用して、空の初期被制御シーケンスを指定するために使用します。

コンストラクター:

`explicit hash_multimap(key_compare^ pred);`

順序述語*pred*、および既定のハッシュ関数を使用して、要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、指定した順序述語と既定のハッシュ関数を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`hash_multimap(key_compare^ pred, hasher^ hashfn);`

順序述語*pred*とハッシュ関数*hashfn*を使用して、要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、指定された順序述語とハッシュ関数を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`hash_multimap(hash_multimap<Key, Mapped>% right);`

既定の順序述語と既定のハッシュ関数を使用して、シーケンス [`right.begin()`、`right.end()`) を使用して被制御シーケンスを初期化します。 これを使用して、hash_multimap オブジェクト*権限*によって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`hash_multimap(hash_multimap<Key, Mapped>^ right);`

既定の順序述語と既定のハッシュ関数を使用して、シーケンス [`right->begin()`、`right->end()`) を使用して被制御シーケンスを初期化します。 これを使用して、hash_multimap オブジェクト*権限*によって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`template<typename InIter> hash_multimap(InIter first, InIter last);`

既定の順序述語と既定のハッシュ関数を使用して、シーケンス [`first`、`last`) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを別のシーケンスのコピーにし、既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred);`

順序述語*pred*を使用し、既定のハッシュ関数を使用して、シーケンス [`first`、`last`) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、指定された順序述語と既定のハッシュ関数を使用して、被制御シーケンスを別のシーケンスのコピーにします。

コンストラクター:

`template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

順序述語*pred*とハッシュ関数*hashfn*を使用して、シーケンス [`first`、`last`) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスに別のシーケンスのコピーを指定し、順序付け述語とハッシュ関数を指定します。

コンストラクター:

`hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right);`

列挙子*権限*によって指定されたシーケンス、既定の順序述語、および既定のハッシュ関数を使用して、被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、列挙子によって記述された別のシーケンスのコピーにし、既定の順序述語とハッシュ関数を使用します。

コンストラクター:

`hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

列挙述語*pred*を使用し、既定のハッシュ関数を使用して、列挙子の*権限*で指定されたシーケンスを使用して、被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、指定した順序述語と既定のハッシュ関数を使用して、列挙子によって記述された別のシーケンスのコピーにします。

コンストラクター:

`hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

順序付け述語*pred*を使用し、ハッシュ関数*hashfn*を使用して、列挙子*権限*によって指定されたシーケンスを使用して被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、列挙述語とハッシュ関数を指定して、列挙子によって記述された別のシーケンスのコピーにします。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_construct.cpp
// compile with: /clr
#include <cliext/hash_map>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
// construct an empty container
    Myhash_multimap c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_multimap c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_multimap c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multimap::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (Myhash_multimap::value_type elem in c2h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_multimap c3(c1.begin(), c1.end());
    for each (Myhash_multimap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_multimap c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (Myhash_multimap::value_type elem in c4)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_multimap c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_multimap::hasher(&myfun));
    for each (Myhash_multimap::value_type elem in c4h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_multimap c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_multimap::value_type>^)%c3);
    for each (Myhash_multimap::value_type elem in c5)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_multimap c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_multimap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>());
    for each (Myhash_multimap::value_type elem in c6)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_multimap c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<
            Myhash_multimap::value_type>^)%c3,
                cliext::greater_equal<wchar_t>(),
                gcnew Myhash_multimap::hasher(&myfun));
    for each (Myhash_multimap::value_type elem in c6h)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_multimap c7(c4);
    for each (Myhash_multimap::value_type elem in c7)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct by copying a container handle
    Myhash_multimap c8(%c3);
    for each (Myhash_multimap::value_type elem in c8)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[a 1] [b 2] [c 3]
size() = 0
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
[c 3] [b 2] [a 1]

[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimaphasher-stlclr"></a><a name="hasher"></a>hash_multimap:: hasher (STL/CLR)

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
// cliext_hash_multimap_hasher.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_multimapinsert-stlclr"></a><a name="insert"></a>hash_multimap:: insert (STL/CLR)

要素を追加します。

### <a name="syntax"></a>構文

```cpp
iterator insert(value_type val);
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

*right*<br/>
挿入する列挙体。

*val*<br/>
挿入するキー値。

*where*<br/>
コンテナー内の挿入位置 (ヒントのみ)。

### <a name="remarks"></a>解説

各メンバー関数は、残りのオペランドによって指定されたシーケンスを挿入します。

1つ目のメンバー関数は、値*val*を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 1つの要素を挿入するために使用します。

2番目のメンバー関数は、(パフォーマンスを向上させるために) ヒントと*してを使用し*て、値*val*を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 これを使用して、既知の要素に隣接している可能性のある単一の要素を挿入します。

3番目のメンバー関数は、シーケンス [`first`、`last`) を挿入します。 このメソッドを使用して、別のシーケンスからコピーされた0個以上の要素を挿入します。

4番目のメンバー関数は、*右側*に指定されたシーケンスを挿入します。 このメソッドを使用して、列挙子によって記述されたシーケンスを挿入します。

各要素の挿入には、被制御シーケンス内の要素数の対数に比例した時間がかかります。 挿入ポイントに隣接する要素を指定するヒントを指定すると、挿入は償却定数時間で実行できます。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_insert.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    Myhash_multimap::iterator it =
        c1.insert(Myhash_multimap::make_value(L'x', 24));
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",
        it->first, it->second);

    it = c1.insert(Myhash_multimap::make_value(L'b', 2));
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",
        it->first, it->second);

    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert a single value with hint
    it = c1.insert(c1.begin(), Myhash_multimap::make_value(L'y', 25));
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",
        it->first, it->second);
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_multimap c2;
    it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_multimap c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::
            IEnumerable<Myhash_multimap::value_type>^)%c1);
    for each (Myhash_multimap::value_type elem in c3)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
insert([L'x' 24]) = [x 24]
insert([L'b' 2]) = [b 2]
[a 1] [b 2] [b 2] [c 3] [x 24]
insert(begin(), [L'y' 25]) = [y 25]
[a 1] [b 2] [b 2] [c 3] [x 24] [y 25]
[a 1] [b 2] [b 2] [c 3] [x 24]
[a 1] [b 2] [b 2] [c 3] [x 24] [y 25]
```

## <a name="hash_multimapiterator-stlclr"></a><a name="iterator"></a>hash_multimap:: iterator (STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの双方向反復子として使用できる、未指定の型 `T1` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("[{0} {1}] ", it->first, it->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapkey_comp-stlclr"></a><a name="key_comp"></a>hash_multimap:: key_comp (STL/CLR)

2つのキーの順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 2 つのキーを比較する場合にこれを使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_key_comp.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multimap c2 = cliext::greater<wchar_t>();
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

## <a name="hash_multimapkey_compare-stlclr"></a><a name="key_compare"></a>hash_multimap:: key_compare (STL/CLR)

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
// cliext_hash_multimap_key_compare.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_multimap c2 = cliext::greater<wchar_t>();
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

## <a name="hash_multimapkey_type-stlclr"></a><a name="key_type"></a>hash_multimap:: key_type (STL/CLR)

順序付けキーの型です。

### <a name="syntax"></a>構文

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター*キー*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_key_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using key_type
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_multimap::key_type val = it->first;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_multimapload_factor-stlclr"></a><a name="load_factor"></a>hash_multimap:: load_factor (STL/CLR)

バケットごとの平均要素数をカウントします。

### <a name="syntax"></a>構文

```cpp
float load_factor();
```

### <a name="remarks"></a>解説

このメンバー関数は、`(float)`[hash_multimap:: size (stl/clr)](../dotnet/hash-multimap-size-stl-clr.md)`() /` [hash_multimap:: bucket_count (stl/clr)](../dotnet/hash-multimap-bucket-count-stl-clr.md)`()`を返します。 この値を使用して、バケットの平均サイズを決定します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_load_factor.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="hash_multimaplower_bound-stlclr"></a><a name="lower_bound"></a>hash_multimap:: lower_bound (STL/CLR)

指定されたキーに一致する範囲の先頭を検索します。

### <a name="syntax"></a>構文

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、*キー*と同じバケットにハッシュし、*キー*と同等の順序を持つ被制御シーケンス内の最初の要素 `X` を決定します。 そのような要素が存在しない場合は、 [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`; を返します。それ以外の場合は、`X`を指定する反復子を返します。 このメソッドを使用して、被制御シーケンスの中で、指定したキーに一致する要素のシーケンスの先頭を検索します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    Myhash_multimap::iterator it = c1.lower_bound(L'a');
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.lower_bound(L'b');
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
lower_bound(L'x')==end() = True
*lower_bound(L'a') = [a 1]
*lower_bound(L'b') = [b 2]
```

## <a name="hash_multimapmake_value-stlclr"></a><a name="make_value"></a>hash_multimap:: make_value (STL/CLR)

値オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
static value_type make_value(key_type key, mapped_type mapped);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
使用するキー値。

*付け*<br/>
検索するマップされた値。

### <a name="remarks"></a>解説

このメンバー関数は、キーが*キー*で、マップされた値が*マップ*されている `value_type` オブジェクトを返します。 これを使用して、他のいくつかのメンバー関数との使用に適したオブジェクトを作成します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_make_value.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapmapped_type-stlclr"></a><a name="mapped_type"></a>hash_multimap:: mapped_type (STL/CLR)

各キーに関連付けられた、マップされた値の型です。

### <a name="syntax"></a>構文

```cpp
typedef Mapped mapped_type;
```

### <a name="remarks"></a>解説

この型は、*マップ*されたテンプレートパラメーターのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_mapped_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using mapped_type
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in mapped_type object
        Myhash_multimap::mapped_type val = it->second;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
1 2 3
```

## <a name="hash_multimapmax_load_factor-stlclr"></a><a name="max_load_factor"></a>hash_multimap:: max_load_factor (STL/CLR)

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

2番目のメンバー関数は、ストアの最大占有率を*new_factor*に置き換えます。 後続の挿入まで自動悪くは発生しません。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="hash_multimapoperator-stlclr"></a><a name="op"></a>hash_multimap:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
hash_multimap<Key, Mapped>% operator=(hash_multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに*right*をコピーし、`*this`を返します。 このメソッドを使用して、被制御シーケンスを*右側*の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_operator_as.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_multimap c2;
    c2 = c1;
// display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimaprbegin-stlclr"></a><a name="rbegin"></a>hash_multimap:: rbegin (STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素、または空のシーケンスの先頭の次の位置を指定する反転反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_rbegin.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_multimap::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*rbegin() = [c 3]
*++rbegin() = [b 2]
```

## <a name="hash_multimapreference-stlclr"></a><a name="reference"></a>hash_multimap:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_reference.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    Myhash_multimap::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_multimap::reference ref = *it;
        System::Console::Write("[{0} {1}] ", ref->first, ref->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="hash_multimaprehash-stlclr"></a><a name="rehash"></a>hash_multimap:: rehash (STL/CLR)

ハッシュ テーブルをリビルドします。

### <a name="syntax"></a>構文

```cpp
void rehash();
```

### <a name="remarks"></a>解説

このメンバー関数は、 [hash_multimap:: load_factor (stl/clr)](../dotnet/hash-multimap-load-factor-stl-clr.md)`() <=` [hash_multimap:: max_load_factor (stl/clr)](../dotnet/hash-multimap-max-load-factor-stl-clr.md)を保証して、ハッシュテーブルを再構築します。 それ以外の場合、ハッシュテーブルのサイズは、挿入後の必要に応じて大きくなります。 (サイズが自動的に縮小されることはありません)。ハッシュテーブルのサイズを調整するには、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_rehash.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1 = gcnew Myhash_multimap;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
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
[a 1] [b 2] [c 3]
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

## <a name="hash_multimaprend-stlclr"></a><a name="rend"></a>hash_multimap:: rend (STL/CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの先頭を越えた位置を示す反転反復子を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_rend.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_multimap::reverse_iterator rit = c1.rend();
    --rit;
    --rit;
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",
        rit->first, rit->second);
    ++rit;
    System::Console::WriteLine("*--rend() = [{0} {1}]",
        rit->first, rit->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
*-- --rend() = [b 2]
*--rend() = [a 1]
```

## <a name="hash_multimapreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>hash_multimap:: reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの反転反復子として使用できる、未指定の型 `T3` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" reversed
    Myhash_multimap::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("[{0} {1}] ", rit->first, rit->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[c 3] [b 2] [a 1]
```

## <a name="hash_multimapsize-stlclr"></a><a name="size"></a>hash_multimap:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスにゼロ以外のサイズがあるかどうかについては、「 [hash_multimap:: empty (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md)`()`」を参照してください。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_size.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(Myhash_multimap::make_value(L'd', 4));
    c1.insert(Myhash_multimap::make_value(L'e', 5));
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="hash_multimapsize_type-stlclr"></a><a name="size_type"></a>hash_multimap:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_size_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_multimap::size_type diff = 0;
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
end()-begin() = 3
```

## <a name="hash_multimapswap-stlclr"></a><a name="swap"></a>hash_multimap:: swap (STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(hash_multimap<Key, Mapped>% right);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

このメンバー関数は、`this` と*right*の間で被制御シーケンスを交換します。 この処理は一定時間に実行され、例外はスローされません。 2つのコンテナーの内容を簡単に交換する方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_swap.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_multimap c2;
    c2.insert(Myhash_multimap::make_value(L'd', 4));
    c2.insert(Myhash_multimap::make_value(L'e', 5));
    c2.insert(Myhash_multimap::make_value(L'f', 6));
    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    for each (Myhash_multimap::value_type elem in c2)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
[d 4] [e 5] [f 6]
[d 4] [e 5] [f 6]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapto_array-stlclr"></a><a name="to_array"></a>hash_multimap:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_to_array.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // copy the container and modify it
    cli::array<Myhash_multimap::value_type>^ a1 = c1.to_array();

    c1.insert(Myhash_multimap::make_value(L'd', 4));
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (Myhash_multimap::value_type elem in a1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3] [d 4]
[a 1] [b 2] [c 3]
```

## <a name="hash_multimapupper_bound-stlclr"></a><a name="upper_bound"></a>hash_multimap:: upper_bound (STL/CLR)

指定されたキーに一致する範囲の末尾を検索します。

### <a name="syntax"></a>構文

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、*キー*と同じバケットにハッシュし、*キー*と同等の順序を持つ被制御シーケンス内の `X` 最後の要素を決定します。 そのような要素が存在しない場合、または被制御シーケンスの最後の要素が `X` の場合は、 [hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`を返します。それ以外の場合は、`X`を超えて最初の要素を指定する反復子を返します。 このメソッドを使用して、被制御シーケンスの中で、指定したキーに一致する要素のシーケンスの末尾を検索します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]"
    for each (Myhash_multimap::value_type elem in c1)
        System::Console::Write("[{0} {1}] ", elem->first, elem->second);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    Myhash_multimap::iterator it = c1.upper_bound(L'a');
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",
        it->first, it->second);
    it = c1.upper_bound(L'b');
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",
        it->first, it->second);
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
upper_bound(L'x')==end() = True
*upper_bound(L'a') = [b 2]
*upper_bound(L'b') = [c 3]
```

## <a name="hash_multimapvalue_comp-stlclr"></a><a name="value_comp"></a>hash_multimap:: value_comp (STL/CLR)

2つの要素の値の順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 これを使用して、2つの要素の値を比較します。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_value_comp.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'b', 2),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = True
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="hash_multimapvalue_compare-stlclr"></a><a name="value_compare"></a>hash_multimap:: value_compare (STL/CLR)

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
// cliext_hash_multimap_value_compare.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_map<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    Myhash_multimap::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",
        kcomp(Myhash_multimap::make_value(L'a', 1),
            Myhash_multimap::make_value(L'b', 2)));
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",
        kcomp(Myhash_multimap::make_value(L'b', 2),
            Myhash_multimap::make_value(L'a', 1)));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare([L'a', 1], [L'a', 1]) = True
compare([L'a', 1], [L'b', 2]) = True
compare([L'b', 2], [L'a', 1]) = False
```

## <a name="hash_multimapvalue_type-stlclr"></a><a name="value_type"></a>hash_multimap:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>解説

この型は `generic_value`の同意語です。

### <a name="example"></a>例

```cpp
// cliext_hash_multimap_value_type.cpp
// compile with: /clr
#include <cliext/hash_map>

typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;
int main()
    {
    Myhash_multimap c1;
    c1.insert(Myhash_multimap::make_value(L'a', 1));
    c1.insert(Myhash_multimap::make_value(L'b', 2));
    c1.insert(Myhash_multimap::make_value(L'c', 3));

    // display contents " [a 1] [b 2] [c 3]" using value_type
    for (Myhash_multimap::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_multimap::value_type val = *it;
        System::Console::Write("[{0} {1}] ", val->first, val->second);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
[a 1] [b 2] [c 3]
```
