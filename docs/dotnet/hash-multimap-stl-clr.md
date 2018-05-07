---
title: hash_multimap (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap
dev_langs:
- C++
helpviewer_keywords:
- hash_multimap class [STL/CLR]
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 027ed43936e4335819f95d10050de37570e6a679
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimap-stlclr"></a>hash_multimap (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`hash_multimap`双方向を格納するテーブルの各エントリをハッシュ テーブルとして要素のシーケンスを管理するには、ノード、および 1 つの要素を格納する各ノードの一覧がリンクされています。 要素は、シーケンスとよいに沿って移動する、マップされた値は、管理するためのキーで構成されます。  
  
 下記に、`GValue`と同じです。  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` 同じ`Key`ref 型を後者には、しない限り、どのケースでは `Key^`  
  
 `GMapped` 同じ`Mapped`ref 型を後者には、しない限り、どのケースでは `Mapped^`  
  
## <a name="syntax"></a>構文  
  
```  
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
  
#### <a name="parameters"></a>パラメーター  
 キー  
 被制御シーケンス内の要素の主要な構成要素の型。  
  
 マップ  
 被制御シーケンス内の要素の追加のコンポーネントの型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[hash_multimap::const_iterator (STL/CLR)](../dotnet/hash-multimap-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[hash_multimap::const_reference (STL/CLR)](../dotnet/hash-multimap-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[hash_multimap::const_reverse_iterator (STL/CLR)](../dotnet/hash-multimap-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[hash_multimap::difference_type (STL/CLR)](../dotnet/hash-multimap-difference-type-stl-clr.md)|2 つの要素間の距離を (場合によっては符号付き) の型。|  
|[hash_multimap::generic_container (STL/CLR)](../dotnet/hash-multimap-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[hash_multimap::generic_iterator (STL/CLR)](../dotnet/hash-multimap-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[hash_multimap::generic_reverse_iterator (STL/CLR)](../dotnet/hash-multimap-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[hash_multimap::generic_value (STL/CLR)](../dotnet/hash-multimap-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[hash_multimap::hasher (STL/CLR)](../dotnet/hash-multimap-hasher-stl-clr.md)|キーのハッシュのデリゲート。|  
|[hash_multimap::iterator (STL/CLR)](../dotnet/hash-multimap-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[hash_multimap::key_compare (STL/CLR)](../dotnet/hash-multimap-key-compare-stl-clr.md)|2 つのキーの順序付けのデリゲート。|  
|[hash_multimap::key_type (STL/CLR)](../dotnet/hash-multimap-key-type-stl-clr.md)|順序付けキーの型です。|  
|[hash_multimap::mapped_type (STL/CLR)](../dotnet/hash-multimap-mapped-type-stl-clr.md)|各キーに関連付けられているマップされた値の型。|  
|[hash_multimap::reference (STL/CLR)](../dotnet/hash-multimap-reference-stl-clr.md)|要素への参照の型です。|  
|[hash_multimap::reverse_iterator (STL/CLR)](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[hash_multimap::size_type (STL/CLR)](../dotnet/hash-multimap-size-type-stl-clr.md)|(負符号) 距離は 2 つの要素の型。|  
|[hash_multimap::value_compare (STL/CLR)](../dotnet/hash-multimap-value-compare-stl-clr.md)|2 つの要素値の順序付けのデリゲート。|  
|[hash_multimap::value_type (STL/CLR)](../dotnet/hash-multimap-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[hash_multimap::begin (STL/CLR)](../dotnet/hash-multimap-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[hash_multimap::bucket_count (STL/CLR)](../dotnet/hash-multimap-bucket-count-stl-clr.md)|バケットの数をカウントします。|  
|[hash_multimap::clear (STL/CLR)](../dotnet/hash-multimap-clear-stl-clr.md)|すべての要素を削除します。|  
|[hash_multimap::count (STL/CLR)](../dotnet/hash-multimap-count-stl-clr.md)|指定したキーに一致する要素の数をカウントします。|  
|[hash_multimap::empty (STL/CLR)](../dotnet/hash-multimap-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[hash_multimap::end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[hash_multimap::equal_range (STL/CLR)](../dotnet/hash-multimap-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[hash_multimap::erase (STL/CLR)](../dotnet/hash-multimap-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[hash_multimap::find (STL/CLR)](../dotnet/hash-multimap-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[hash_multimap::hash_delegate (STL/CLR)](../dotnet/hash-multimap-hash-delegate-stl-clr.md)|キーのハッシュのデリゲートをコピーします。|  
|[hash_multimap::hash_multimap (STL/CLR)](../dotnet/hash-multimap-hash-multimap-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[hash_multimap::insert (STL/CLR)](../dotnet/hash-multimap-insert-stl-clr.md)|要素を追加します。|  
|[hash_multimap::key_comp (STL/CLR)](../dotnet/hash-multimap-key-comp-stl-clr.md)|2 つのキーの順序付けのデリゲートをコピーします。|  
|[hash_multimap::load_factor (STL/CLR)](../dotnet/hash-multimap-load-factor-stl-clr.md)|バケットごとの平均要素数をカウントします。|  
|[hash_multimap::lower_bound (STL/CLR)](../dotnet/hash-multimap-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検出します。|  
|[hash_multimap::make_value (STL/CLR)](../dotnet/hash-multimap-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[hash_multimap::max_load_factor (STL/CLR)](../dotnet/hash-multimap-max-load-factor-stl-clr.md)|バケットあたりの最大要素数を取得または設定します。|  
|[hash_multimap::rbegin (STL/CLR)](../dotnet/hash-multimap-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[hash_multimap::rehash (STL/CLR)](../dotnet/hash-multimap-rehash-stl-clr.md)|ハッシュ テーブルをリビルドします。|  
|[hash_multimap::rend (STL/CLR)](../dotnet/hash-multimap-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[hash_multimap::size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md)|要素の数をカウントします。|  
|[hash_multimap::swap (STL/CLR)](../dotnet/hash-multimap-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[hash_multimap::to_array (STL/CLR)](../dotnet/hash-multimap-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[hash_multimap::upper_bound (STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[hash_multimap::value_comp (STL/CLR)](../dotnet/hash-multimap-value-comp-stl-clr.md)|2 つの要素値の順序付けのデリゲートをコピーします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[hash_multimap::operator= (STL/CLR)](../dotnet/hash-multimap-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|IHash\<キー、値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、双方向のリンク リスト内の個々 のノードとして、制御するシーケンスの記憶域を解放します。 アクセスを高速化、オブジェクトのサブリストのシーケンスとしてリスト全体を効果的に管理する (ハッシュ テーブル) の場合は、リストへのポインターの可変長配列を保持するか、バケットします。 順序付けられた 1 つのノードの内容を別にコピーからではなく、ノード間のリンクを変更することにより保持されるバケットに要素を挿入します。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。  
  
 オブジェクトが各バケット ストアド デリゲート型のオブジェクトを呼び出すことによって、制御を注文[hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md)です。 Hash_set; を作成する場合は、ストアド デリゲート オブジェクトを指定することができます。デリゲート オブジェクトを指定しないと、既定値が比較`operator<=(key_type, key_type)`です。  
  
 このメンバー関数を呼び出すことによってストアド デリゲート オブジェクトにアクセスする[hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`です。 このようなデリゲート オブジェクトが型のキーと同じ順序を定義する必要があります[hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `key_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`key_comp()(X, Y) && key_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 ように動作している順序ルール`operator<=(key_type, key_type)`、`operator>=(key_type, key_type)`または`operator==(key_type, key_type)`eqivalent 順序を定義します。  
  
 コンテナーが保証されるだけ要素キーを持つと同じ順序 (あり同じ整数値にどのハッシュ) が、バケット内で隣接する注意してください。 テンプレート クラスとは異なり[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)、テンプレート クラスのオブジェクト`hash_multimap`すべての要素のキーが一意であることは不要です。 (2 つまたは複数のキーが持てると同じ順序です。)  
  
 オブジェクトを決定するバケット ストアド デリゲート型のオブジェクトを呼び出すことによって指定された順序付けキーを含める必要があります[hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md)です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()`キーの値に依存する整数値を取得します。 Hash_set; を作成する場合は、ストアド デリゲート オブジェクトを指定することができます。既定値は、関数、デリゲート オブジェクトを指定しない場合`System::Object::hash_value(key_type)`です。 つまり、すべてのキーの`X`と`Y`:  
  
 `hash_delegate()(X)` すべての呼び出しで同じ結果の整数値を返します。  
  
 場合`X`と`Y`大小関係が等しい、し`hash_delegate()(X)`として同じ整数の結果を返す必要があります`hash_delegate()(Y)`です。  
  
 各要素には、個別のキーと、マップされた値が含まれています。 シーケンスは、検索、挿入、削除、任意の要素内にある (定数時間)--シーケンス内の要素の数とは無関係には、少なくともケースの最適な操作の数にできるような方法で表されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 ハッシュされた値が均等に分散していない場合、ハッシュ テーブルは逆ことができます。 常に同じの値を返す--ハッシュ関数の場合--極度の検索、挿入、削除は、シーケンス (線形時間) 内の要素の数に比例します。 コンテナーが妥当なハッシュ関数、バケットの平均サイズを選択するよう努めてし、ハッシュ テーブルのサイズ (バケットの合計数) ですが、これらのオプションの一部またはすべてをオーバーライドできます。 関数を参照して、 [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md)と[hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md)です。  
  
 Hash_multimap は、被制御シーケンス内の要素を指定する反復子を指定する、隣接する要素をステップ実行できますが、双方向反復子をサポートします。 特殊なヘッド ノードによって返される反復子に対応[hash_multimap::end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達する hash_multimap 反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定 hash_multimap の要素を参照することはできないことに注意してください。  
  
 Hash_multimap の反復子は、それに関連付けられているコンテナーへのハンドルを格納する関連付けられた hash_multimap ノードへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 Hash_multimap の反復子は、関連付けられている hash_multimap ノードにいくつかの hash_multimap に関連付けられている限り有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)