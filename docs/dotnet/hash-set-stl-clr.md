---
title: hash_set (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9c701bfa64e96594050ddaf46d56c12849a0ad30
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079750"
---
# <a name="hashset-stlclr"></a>hash_set (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`hash_set`双方向を格納するテーブルの各エントリをハッシュ テーブルとして要素のシーケンスを管理するには、ノード、および 1 つの要素を格納する各ノードの一覧がリンクされています。 各要素の値は、シーケンスの順序で、キーとして使用されます。  
  
 下記に、`GValue`と同じ`GKey`、さらには同じ`Key`ref 型を後者には、しない限り、どのケースでは`Key^`です。  
  
## <a name="syntax"></a>構文  
  
```  
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
 キー  
 被制御シーケンス内の要素の主要な構成要素の型。  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  

## <a name="declarations"></a>宣言  
  
|型定義|説明|  
|---------------------|-----------------|  
|[hash_set::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|  
|[hash_set::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|  
|[hash_set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|  
|[hash_set::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を (場合によっては符号付き) の型。|  
|[hash_set::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリック インターフェイスの型。|  
|[hash_set::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[hash_set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[hash_set::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[hash_set::hasher (STL/CLR)](#hasher)|キーのハッシュのデリゲート。|  
|[hash_set::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|  
|[hash_set::key_compare (STL/CLR)](#key_compare)|2 つのキーの順序付けのデリゲート。|  
|[hash_set::key_type (STL/CLR)](#key_type)|順序付けキーの型です。|  
|[hash_set::reference (STL/CLR)](#reference)|要素への参照の型です。|  
|[hash_set::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|  
|[hash_set::size_type (STL/CLR)](#size_type)|(負符号) 距離は 2 つの要素の型。|  
|[hash_set::value_compare (STL/CLR)](#value_compare)|2 つの要素値の順序付けのデリゲート。|  
|[hash_set::value_type (STL/CLR)](#value_type)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[hash_set::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|  
|[hash_set::bucket_count (STL/CLR)](#bucket_count)|バケットの数をカウントします。|  
|[hash_set::clear (STL/CLR)](#clear)|すべての要素を削除します。|  
|[hash_set::count (STL/CLR)](#count)|指定したキーに一致する要素の数をカウントします。|  
|[hash_set::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|  
|[hash_set::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|  
|[hash_set::equal_range (STL/CLR)](#equal_range)|指定したキーに一致する範囲を検索します。|  
|[hash_set::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|  
|[hash_set::find (STL/CLR)](#find)|指定したキーに一致する要素を検索します。|  
|[hash_set::hash_delegate (STL/CLR)](#hash_delegate)|キーのハッシュのデリゲートをコピーします。|  
|[hash_set::hash_set (STL/CLR)](#hash_set)|コンテナー オブジェクトを構築します。|  
|[hash_set::insert (STL/CLR)](#insert)|要素を追加します。|  
|[hash_set::key_comp (STL/CLR)](#key_comp)|2 つのキーの順序付けのデリゲートをコピーします。|  
|[hash_set::load_factor (STL/CLR)](#load_factor)|バケットごとの平均要素数をカウントします。|  
|[hash_set::lower_bound (STL/CLR)](#lower_bound)|指定したキーに一致する範囲の先頭を検出します。|  
|[hash_set::make_value (STL/CLR)](#make_value)|値オブジェクトを構築します。|  
|[hash_set::max_load_factor (STL/CLR)](#max_load_factor)|バケットあたりの最大要素数を取得または設定します。|  
|[hash_set::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|  
|[hash_set::rehash (STL/CLR)](#rehash)|ハッシュ テーブルをリビルドします。|  
|[hash_set::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|  
|[hash_set::size (STL/CLR)](#size)|要素の数をカウントします。|  
|[hash_set::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|  
|[hash_set::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|  
|[hash_set::upper_bound (STL/CLR)](#upper_bound)|指定したキーに一致する範囲の末尾を検索します。|  
|[hash_set::value_comp (STL/CLR)](#value_comp)|2 つの要素値の順序付けのデリゲートをコピーします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[hash_set::operator= (STL/CLR)](#op)|被制御シーケンスを置き換えます。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|IHash\<キー、値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>Remarks  
 オブジェクトは、割り当てし、双方向のリンク リスト内の個々 のノードとして、制御するシーケンスの記憶域を解放します。 アクセスを高速化、オブジェクトのサブリストのシーケンスとしてリスト全体を効果的に管理する (ハッシュ テーブル) の場合は、リストへのポインターの可変長配列を保持するか、バケットします。 順序付けられた 1 つのノードの内容を別にコピーからではなく、ノード間のリンクを変更することにより保持されるバケットに要素を挿入します。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。  
  
 オブジェクトが各バケット ストアド デリゲート型のオブジェクトを呼び出すことによって、制御を注文[hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)です。 Hash_set; を作成する場合は、ストアド デリゲート オブジェクトを指定することができます。デリゲート オブジェクトを指定しないと、既定値が比較`operator<=(key_type, key_type)`です。  
  
 このメンバー関数を呼び出すことによってストアド デリゲート オブジェクトにアクセスする[hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`です。 このようなデリゲート オブジェクトが型のキーと同じ順序を定義する必要があります[hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `key_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`key_comp()(X, Y) && key_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 ように動作している順序ルール`operator<=(key_type, key_type)`、`operator>=(key_type, key_type)`または`operator==(key_type, key_type)`eqivalent 順序を定義します。  
  
 コンテナーが保証されるだけ要素キーを持つと同じ順序 (あり同じ整数値にどのハッシュ) が、バケット内で隣接する注意してください。 テンプレート クラスとは異なり[hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)、テンプレート クラスのオブジェクト`hash_set`すべての要素のキーが一意であることを確認します。 (2 つのキーも大小関係が等しい。)  
  
 オブジェクトを決定するバケット ストアド デリゲート型のオブジェクトを呼び出すことによって指定された順序付けキーを含める必要があります[hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()`キーの値に依存する整数値を取得します。 Hash_set; を作成する場合は、ストアド デリゲート オブジェクトを指定することができます。既定値は、関数、デリゲート オブジェクトを指定しない場合`System::Object::hash_value(key_type)`です。 つまり、すべてのキーの`X`と`Y`:  
  
 `hash_delegate()(X)` すべての呼び出しで同じ結果の整数値を返します。  
  
 場合`X`と`Y`大小関係が等しい、し`hash_delegate()(X)`として同じ整数の結果を返す必要があります`hash_delegate()(Y)`です。  
  
 各要素は、キーと値の両方として機能します。 シーケンスは、検索、挿入、削除、任意の要素内にある (定数時間)--シーケンス内の要素の数とは無関係には、少なくともケースの最適な操作の数にできるような方法で表されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 ハッシュされた値が均等に分散していない場合、ハッシュ テーブルは逆ことができます。 常に同じの値を返す--ハッシュ関数の場合--極度の検索、挿入、削除は、シーケンス (線形時間) 内の要素の数に比例します。 コンテナーが妥当なハッシュ関数、バケットの平均サイズを選択するよう努めてし、ハッシュ テーブルのサイズ (バケットの合計数) ですが、これらのオプションの一部またはすべてをオーバーライドできます。 関数を参照して、 [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md)と[hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)です。  
  
 Hash_set は、ステップ隣接する要素を被制御シーケンス内の要素を指定する反復子を指定することができますが、双方向反復子をサポートします。 特殊なヘッド ノードによって返される反復子に対応[hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達する hash_set 反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定 hash_set の要素を参照することはできないことに注意してください。  
  
 Hash_set の反復子は、それに関連付けられているコンテナーへのハンドルを格納する関連付けられた hash_set ノードへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 Hash_set の反復子は、関連付けられている hash_set ノードにいくつかの hash_set に関連付けられている限り有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="members"></a>メンバー

## <a name="begin"></a> hash_set::begin (STL/CLR)
被制御シーケンスの先頭を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、または空のシーケンスの最後を越えたところ、被制御シーケンスの最初の要素を指定する双方向反復子を返します。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さが変更された場合は、被制御シーケンスが、そのステータスの先頭を変更できます。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Myhash_set::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  

## <a name="bucket_count"></a> hash_set::bucket_count (STL/CLR)
バケットの数をカウントします。  
  
### <a name="syntax"></a>構文  
  
```  
int bucket_count();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数では、現在のバケット数を返します。 使用するハッシュ テーブルのサイズを決定します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="clear"></a> hash_set::clear (STL/CLR)
すべての要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数が効果的に呼び出し[hash_set::erase (STL/CLR)](../dotnet/hash-set-erase-stl-clr.md) `(` [hash_set::begin (STL/CLR)](../dotnet/hash-set-begin-stl-clr.md) `(),` [hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`())`. これを使用するには、被制御シーケンスが空であることを確認します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
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

## <a name="const_iterator"></a> hash_set::const_iterator (STL/CLR)
被制御シーケンスの定数反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T2`被制御シーケンスの定数の双方向反復子として使用されることができます。  
  
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
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> hash_set::const_reference (STL/CLR)
要素への定数参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Remarks  
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
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reverse_iterator"></a> hash_set::const_reverse_iterator (STL/CLR)
被制御シーケンスの定数反転反復子の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T4`被制御シーケンスの定数反転反復子として使用されることができます。  
  
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
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="count"></a> hash_set::count (STL/CLR)
指定したキーに一致する要素の数を検索します。  
  
### <a name="syntax"></a>構文  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数と同じ順序付けする被制御シーケンスの要素の数を返します`key`です。 それを使用して、指定したキーと一致する、被制御シーケンスの現在の要素の数を決定します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="difference_type"></a> hash_set::difference_type (STL/CLR)
2 つの要素間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、可能性のある負の値の要素の数を表します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="empty"></a> hash_set::empty (STL/CLR)
要素が存在しないかどうかをテストします。  
  
### <a name="syntax"></a>構文  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスが空の場合に true を返します。 等価である[hash_set::size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md)`() == 0`です。 これを使用するには、hash_set が空かどうかをテストします。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="end"></a> hash_set::end (STL/CLR)
被制御シーケンスの末尾を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの最後の位置を指し示す双方向反復子を返します。 被制御シーケンスの末尾を指定する反復子を取得するのにために使用します。その状態は、被制御シーケンスの長さが変更された場合は変更されません。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="equal_range"></a> hash_set::equal_range (STL/CLR)
指定したキーに一致する範囲を検索します。  
  
### <a name="syntax"></a>構文  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数が組の反復子を返します`cliext::pair<iterator, iterator>(` [hash_set::lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md) `(key),` [hash_set::upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)`(key))`です。 使用する指定したキーと一致する、被制御シーケンスの現在の要素の範囲が決まります。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
``` 

## <a name="erase"></a> hash_set::erase (STL/CLR)
指定した位置にある要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 消去する範囲の開始しています。  
  
 key  
 消去するキー値。  
  
 last  
 消去する範囲の終了。  
  
 where  
 消去する要素。  
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数によって示される、被制御シーケンスの要素を削除する`where`、し、削除、要素の後に残る最初の要素を指定する反復子を返しますまたは[hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`このような要素が存在しない場合。 それを使用するには 1 つの要素を削除します。  
  
 2 番目のメンバー関数、被制御シーケンスの要素の範囲内の削除 [`first`、 `last`)、し、削除された要素の後に残る最初の要素を指定する反復子を返しますまたは`end()`場合、このような要素がないです。存在する. これを使用するには 0 個以上の連続する要素を削除します。  
  
 3 番目のメンバー関数と同じ順序キーを持つは、被制御シーケンスのいずれかの要素を削除する`key`、削除された要素の数のカウントを返します。 これを使用して、削除し、指定したキーと一致するすべての要素をカウントします。  
  
 各要素の消去では、被制御シーケンス内の要素の数の対数に比例して時間がかかります。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
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

## <a name="find"></a> hash_set::find (STL/CLR)
指定したキーに一致する要素を検索します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
### <a name="remarks"></a>Remarks  
 被制御シーケンス内の少なくとも 1 つの要素と同じ順序付け`key`、メンバー関数は、それらの要素のいずれかを指定する反復子を返しますそれ以外の場合を返します[hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`。 指定したキーに一致する制御シーケンス内の要素を検索に使用するとします。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="generic_container"></a> hash_set::generic_container (STL/CLR)
コンテナーのジェネリック インターフェイスの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IHash<GKey, GValue>  
    generic_container;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスを表します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.insert(L'e');   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
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

## <a name="generic_iterator"></a> hash_set::generic_iterator (STL/CLR)
コンテナーのジェネリック インターフェイスを使用するため、反復子の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスで使用できる汎用の反復子を表します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_set::generic_iterator gcit = gc1->begin();   
    Myhash_set::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a  
```  

## <a name="generic_reverse_iterator"></a> hash_set::generic_reverse_iterator (STL/CLR)
コンテナーのジェネリック インターフェイスを使用する反転反復子の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value>  
    generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレートのコンテナー クラスのジェネリック インターフェイスで使用できる汎用反転反復子を表します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_set::generic_reverse_iterator gcit = gc1->rbegin();   
    Myhash_set::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
c  
```  
  
## <a name="generic_value"></a> hash_set::generic_value (STL/CLR)
コンテナーのジェネリック インターフェイスを使用するための要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、型のオブジェクトを表します。`GValue`ストアド要素の値をこのテンプレートのコンテナー クラスのジェネリック インターフェイスを使用することについて説明します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_set::generic_iterator gcit = gc1->begin();   
    Myhash_set::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a  
```  

## <a name="hash_delegate"></a> hash_set::hash_delegate (STL/CLR)
指定したキーに一致する要素を検索します。  
  
### <a name="syntax"></a>構文  
  
```  
hasher^ hash_delegate();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、キーの値を整数に変換するために使用されるデリゲートを返します。 キーのハッシュに使用するとします。  
  
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

## <a name="hash_set"></a> hash_set::hash_set (STL/CLR)
コンテナー オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
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
 先頭  
 挿入する範囲の開始しています。  
  
 hashfn  
 ハッシュ バケットにマッピング キーの関数。  
  
 last  
 挿入する範囲の終了。  
  
 pred  
 被制御シーケンスの述語を順序付けです。  
  
 右  
 挿入するオブジェクトまたは範囲。  
  
### <a name="remarks"></a>Remarks  
 : コンス トラクター  
  
 `hash_set();`  
  
 既定の順序の述語を使用して要素を持たない、被制御シーケンスを初期化`key_compare()`既定のハッシュ関数を使用しています。 これを使用するには、既定の述語とハッシュ関数の順序を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `explicit hash_set(key_compare^ pred);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`既定のハッシュ関数を使用しています。 これを使用するには、空の初期被制御シーケンスを指定された順序の指定の述語と既定のハッシュ関数を指定します。  
  
 : コンス トラクター  
  
 `hash_set(key_compare^ pred, hasher^ hashfn);`  
  
 順序の指定の述語での要素を持たない被制御シーケンスを初期化します`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用して、指定の順序の指定の述語とハッシュ関数で、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `hash_set(hash_set<Key>% right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right.begin()`、 `right.end()`)、既定の順序の述語、および既定のハッシュ関数です。 Hash_set オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の指定の述語とハッシュ関数を使用します。  
  
 : コンス トラクター  
  
 `hash_set(hash_set<Key>^ right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right->begin()`、 `right->end()`)、既定の順序の述語、および既定のハッシュ関数です。 Hash_set オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`既定の順序の指定の述語とハッシュ関数を使用します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_set(InIter first, InIter last);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`first`、 `last`)、既定の順序の述語、および既定のハッシュ関数です。 使用する既定の順序の述語とハッシュ関数で被制御シーケンスの別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、順序の指定の述語に置き換えます`pred`既定のハッシュ関数を使用しています。 これを使用するには、被制御シーケンスの順序指定された述語と既定のハッシュ関数、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 シーケンスに、被制御シーケンスを初期化します [`first`、 `last`)、順序の指定の述語と`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用するには、被制御シーケンスの指定の順序の指定の述語とハッシュ関数で、別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`既定の順序の述語、および既定のハッシュ関数です。 これを使用するには、被制御シーケンスの既定の順序の述語とハッシュ関数と、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語に置き換えます`pred`既定のハッシュ関数を使用しています。 これを使用するには、被制御シーケンスに指定された順序の指定の述語と既定ハッシュ関数、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`、順序の指定の述語と`pred`、ハッシュ関数を使用して`hashfn`です。 これを使用するには、被制御シーケンスの指定の順序の指定の述語とハッシュ関数で、列挙子によって記述された別のシーケンスのコピーを作成します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_set c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_set c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_set c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_set c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_set c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_set c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_set c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_set c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_set c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
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

## <a name="hasher"></a> hash_set::hasher (STL/CLR)
キーのハッシュのデリゲート。  
  
### <a name="syntax"></a>構文  
  
```  
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>  
    hasher;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、キーの値を整数に変換するデリゲートを表します。  
  
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

## <a name="insert"></a> hash_set::insert (STL/CLR)
要素を追加します。  
  
### <a name="syntax"></a>構文  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 右  
 列挙型を挿入します。  
  
 Val  
 挿入するキー値。  
  
 where  
 (ヒントのみ) を挿入するためのコンテナー内の場所。  
  
### <a name="remarks"></a>Remarks  
 各メンバー関数は、残りのオペランドで指定されたシーケンスを挿入します。  
  
 最初のメンバー関数が値を持つ要素を挿入するよう努めて`val`、値のペアを返しますと`X`です。 場合`X.second`が true の場合、`X.first`新しく挿入される要素を指定以外の場合`X.first`それと同等の要素を指定既に順序付けが存在し、新しい要素が挿入されません。 使用する 1 つの要素を挿入します。  
  
 2 番目のメンバー関数は、値を持つ要素を挿入します。`val`を使用して、 `where` (パフォーマンスを向上させる) をヒントとしてし、新しく挿入される要素を指定する反復子を返します。 使用することがわかって要素に隣接する可能性のある 1 つの要素を挿入します。  
  
 3 番目のメンバー関数は、シーケンスを挿入します。 [`first`、 `last`)。 使用する別のシーケンスからコピーした 0 個以上の要素を挿入します。  
  
 4 番目のメンバー関数で指定されたシーケンスを挿入する、`right`です。 使用する列挙子によって説明されているシーケンスを挿入します。  
  
 各要素の挿入では、被制御シーケンス内の要素の数の対数に比例して時間がかかります。 挿入は、カーソル位置に隣接する要素を指定するヒントの指定、償却定数時間でただし、実行できます。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_set c2;   
    Myhash_set::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_set c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
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

## <a name="iterator"></a> hash_set::iterator (STL/CLR)
被制御シーケンスの反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T1`被制御シーケンスの双方向反復子として使用されることができます。  
  
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
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="key_comp"></a> hash_set::key_comp (STL/CLR)
2 つのキーの順序付けのデリゲートをコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
key_compare^key_comp();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数では、被制御シーケンスの並べ替えに使用される順序付けのデリゲートを返します。 2 つのキーの比較に使用するとします。  
  
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

## <a name="key_comp"></a> hash_set::key_comp (STL/CLR)
2 つのキーの順序付けのデリゲートをコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
key_compare^key_comp();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数では、被制御シーケンスの並べ替えに使用される順序付けのデリゲートを返します。 2 つのキーの比較に使用するとします。  
  
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

## <a name="key_compare"></a> hash_set::key_compare (STL/CLR)
2 つのキーの順序付けのデリゲート。  
  
### <a name="syntax"></a>構文  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
### <a name="remarks"></a>Remarks  
 型は、そのキーの引数の順序を決定するデリゲートのシノニムです。  
  
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

## <a name="key_type"></a> hash_set::key_type (STL/CLR)
順序付けキーの型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーター `Key` のシノニムです。  
  
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
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="load_factor"></a> hash_set::load_factor (STL/CLR)
バケットごとの平均要素数をカウントします。  
  
### <a name="syntax"></a>構文  
  
```  
float load_factor();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数を返します`(float)` [hash_set::size (STL/CLR)](../dotnet/hash-set-size-stl-clr.md) `() /` [hash_set::bucket_count (STL/CLR)](../dotnet/hash-set-bucket-count-stl-clr.md)`()`です。 使用するバケットの平均サイズを決定します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="lower_bound"></a> hash_set::lower_bound (STL/CLR)
指定したキーに一致する範囲の先頭を検出します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、最初の要素を決定する`X`同じバケットにハッシュされる被制御シーケンス内`key`と同じ順序が`key`です。 このような要素が存在しないかどうかが返されます[hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`; 指定する反復子を返しますそれ以外の場合`X`です。 これを使用して、指定したキーと一致する、被制御シーケンス内で現在の要素のシーケンスの先頭を検索します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="make_value"></a> hash_set::make_value (STL/CLR)
値オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
static value_type make_value(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 使用するキー値。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数を返します、`value_type`オブジェクト キーを持つ`key`します。 他のいくつかのメンバー関数で使用するために適切なオブジェクトの作成に使用するとします。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="max_load_factor"></a> hash_set::max_load_factor (STL/CLR)
バケットあたりの最大要素数を取得または設定します。  
  
### <a name="syntax"></a>構文  
  
```  
float max_load_factor();  
void max_load_factor(float new_factor);  
```  
  
#### <a name="parameters"></a>パラメーター  
 new_factor  
 新しい最大値を格納する要素を読み込みます。  
  
### <a name="remarks"></a>Remarks  
 最初のメンバー関数は、現在格納されている最大占有率を返します。 使用する最大バケットの平均サイズを決定します。  
  
 2 番目のメンバー関数とストアの最大テーブル占有率が置き換えられます`new_factor`です。 自動再ハッシュは行われませんまで後続の挿入します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="op"></a> hash_set::operator = (STL/CLR)
被制御シーケンスを置き換えます。  
  
### <a name="syntax"></a>構文  
  
```  
hash_set<Key>% operator=(hash_set<Key>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするコンテナー。  
  
### <a name="remarks"></a>Remarks  
 メンバー演算子コピー`right`オブジェクトを返します`*this`です。 これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーと置き換えます。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myhash_set c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Myhash_set::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="rbegin"></a> hash_set::rbegin (STL/CLR)
反転被制御シーケンスの先頭を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、最後の要素または空のシーケンスの先頭を越えた、被制御シーケンスの指定、逆順反復子を返します。 したがって、これを指定、`beginning`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合、逆の順序で表示される、被制御シーケンスですがその状態の先頭は変更できます。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="reference"></a> hash_set::reference (STL/CLR)
要素への参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Remarks  
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
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="rehash"></a> hash_set::rehash (STL/CLR)
ハッシュ テーブルをリビルドします。  
  
### <a name="syntax"></a>構文  
  
```  
void rehash();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、ことを確認する、ハッシュ テーブルをリビルド[hash_set::load_factor (STL/CLR)](../dotnet/hash-set-load-factor-stl-clr.md) `() <=` [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md)です。 それ以外の場合、挿入後に必要な場合のみ、ハッシュ テーブルはサイズで増加します。 (が自動的にサイズは小さくなります。)使用するハッシュ テーブルのサイズを調整します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="rend"></a> hash_set::rend (STL/CLR)
反転被制御シーケンスの末尾を指定します。  
  
### <a name="syntax"></a>構文  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの先頭位置を指し示す反転反復子を返します。 したがって、これを指定、`end`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合は逆の順序で表示される、被制御シーケンスですがその状態の終了を変更できます。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="reverse_iterator"></a> hash_set::reverse_iterator (STL/CLR)
被制御シーケンスの反転反復子の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Remarks  
 この型が指定されていない型のオブジェクトを表します`T3`被制御シーケンスの反転反復子として使用されることができます。  
  
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
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="size"></a> hash_set::size (STL/CLR)
要素の数をカウントします。  
  
### <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの長さを返します。 これを使用するには、被制御シーケンス内の現在の要素の数を決定します。 シーケンスが参照してください、0 以外のサイズを持つかどうかは、関心のあるすべて場合[hash_set::empty (STL/CLR)](../dotnet/hash-set-empty-stl-clr.md)`()`です。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="size_type"></a> hash_set::size_type (STL/CLR)
2 つの要素の間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、負でない要素の数を表します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="swap"></a> hash_set::swap (STL/CLR)
2 つのコンテナーのコンテンツを交換します。  
  
### <a name="syntax"></a>構文  
  
```  
void swap(hash_set<Key>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コンテンツを交換するコンテナー。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、`this` と `right` の間で被制御シーケンスを交換します。 定数時間では、例外をスローしません。 2 つのコンテナーの内容を交換する簡単な方法として使用するとします。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Myhash_set c2;   
    c2.insert(L'd');   
    c2.insert(L'e');   
    c2.insert(L'f');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
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

## <a name="to_array"></a> hash_set::to_array (STL/CLR)
被制御シーケンスを新しい配列にコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
cli::array<value_type>^ to_array();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、被制御シーケンスを格納する配列を返します。 使用する配列形式の被制御シーケンスのコピーを入手します。  
  
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
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  

## <a name="upper_bound"></a> hash_set::upper_bound (STL/CLR)
指定したキーに一致する範囲の末尾を検索します。  
  
### <a name="syntax"></a>構文  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数の最後の要素を決定する`X`同じバケットにハッシュされる被制御シーケンス内`key`と同じ順序が`key`です。 このような要素が存在しない場合、または場合`X`、被制御シーケンスの最後の要素では返します[hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`;最初の要素を指定する反復子を返しますそれ以外の場合`X`. これを使用して、指定したキーと一致する、被制御シーケンス内で現在の要素のシーケンスの末尾を検索します。  
  
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
        System::Console::Write(" {0}", elem);   
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

## <a name="value_comp"></a> hash_set::value_comp (STL/CLR)
2 つの要素値の順序付けのデリゲートをコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
value_compare^ value_comp();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数では、被制御シーケンスの並べ替えに使用される順序付けのデリゲートを返します。 使用する 2 つの要素値を比較します。  
  
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

## <a name="value_compare"></a> hash_set::value_compare (STL/CLR)
2 つの要素値の順序付けのデリゲート。  
  
### <a name="syntax"></a>構文  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
### <a name="remarks"></a>Remarks  
 型は、その値の引数の順序を決定するデリゲートのシノニムです。  
  
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

## <a name="value_type"></a> hash_set::value_type (STL/CLR)
要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef generic_value value_type;  
```  
  
### <a name="remarks"></a>Remarks  
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
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  