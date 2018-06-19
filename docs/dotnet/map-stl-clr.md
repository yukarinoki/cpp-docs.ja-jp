---
title: マップ (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cda679ed01e5266f0605639df45940d8f17e506d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137791"
---
# <a name="map-stlclr"></a>map (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`map`1 つの要素を格納する各ノードのバランスの取れた (ほとんど) の順序付けられたツリーとして要素のシーケンスを管理します。 要素は、シーケンスとよいに沿って移動する、マップされた値は、管理するためのキーで構成されます。  
  
 下記に、`GValue`と同じです。  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` 同じ`Key`ref 型を後者には、しない限り、どのケースでは `Key^`  
  
 `GMapped` 同じ`Mapped`ref 型を後者には、しない限り、どのケースでは `Mapped^`  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
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
|[map::const_iterator (STL/CLR)](../dotnet/map-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[map::const_reference (STL/CLR)](../dotnet/map-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[map::const_reverse_iterator (STL/CLR)](../dotnet/map-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[map::difference_type (STL/CLR)](../dotnet/map-difference-type-stl-clr.md)|2 つの要素間の距離を (場合によっては符号付き) の型。|  
|[map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[map::generic_value (STL/CLR)](../dotnet/map-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[map::iterator (STL/CLR)](../dotnet/map-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)|2 つのキーの順序付けのデリゲート。|  
|[map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)|順序付けキーの型です。|  
|[map::mapped_type (STL/CLR)](../dotnet/map-mapped-type-stl-clr.md)|各キーに関連付けられているマップされた値の型。|  
|[map::reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)|要素への参照の型です。|  
|[map::reverse_iterator (STL/CLR)](../dotnet/map-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[map::size_type (STL/CLR)](../dotnet/map-size-type-stl-clr.md)|(負符号) 距離は 2 つの要素の型。|  
|[map::value_compare (STL/CLR)](../dotnet/map-value-compare-stl-clr.md)|2 つの要素値の順序付けのデリゲート。|  
|[map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[map::clear (STL/CLR)](../dotnet/map-clear-stl-clr.md)|すべての要素を削除します。|  
|[map::count (STL/CLR)](../dotnet/map-count-stl-clr.md)|指定したキーに一致する要素の数をカウントします。|  
|[map::empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[map::find (STL/CLR)](../dotnet/map-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[map::insert (STL/CLR)](../dotnet/map-insert-stl-clr.md)|要素を追加します。|  
|[map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)|2 つのキーの順序付けのデリゲートをコピーします。|  
|[map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検出します。|  
|[map::make_value (STL/CLR)](../dotnet/map-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[map::map (STL/CLR)](../dotnet/map-map-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[map::rbegin (STL/CLR)](../dotnet/map-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[map::size (STL/CLR)](../dotnet/map-size-stl-clr.md)|要素の数をカウントします。|  
|[map::swap (STL/CLR)](../dotnet/map-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[map::to_array (STL/CLR)](../dotnet/map-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[map::value_comp (STL/CLR)](../dotnet/map-value-comp-stl-clr.md)|2 つの要素値の順序付けのデリゲートをコピーします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[map::operator= (STL/CLR)](../dotnet/map-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[map::operator(STL/CLR)](../dotnet/map-operator-stl-clr.md)|関連するマップされた値をキーにマップします。|  
|[operator!= (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)|かどうかを`map`オブジェクトが他と等しくない`map`オブジェクト。|  
|[operator< (map) (STL/CLR)](../dotnet/operator-less-than-map-stl-clr.md)|かどうかを`map`オブジェクトが他よりも小さい`map`オブジェクト。|  
|[operator<= (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)|かどうかを`map`オブジェクトが別に小さい`map`オブジェクト。|  
|[operator== (map) (STL/CLR)](../dotnet/operator-equality-map-stl-clr.md)|かどうかを`map`オブジェクトが他と等しい`map`オブジェクト。|  
|[operator> (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)|かどうかを`map`オブジェクトが他よりも大きい`map`オブジェクト。|  
|[operator>= (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|かどうかを`map`オブジェクトがより大きいか等しい間`map`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|<xref:System.Collections.Generic.IDictionary%602>|{キー、値} のグループの管理のペア。|  
|ITree < Key, 値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、個々 のノードとして、制御するシーケンスの記憶域を解放します。 順序付けられた 1 つのノードの内容を別にコピーからではなく、ノード間のリンクを変更することにより保持される (ほとんど) バランスの良いツリーに要素を挿入します。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。  
  
 オブジェクトがストアド デリゲート型のオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます[map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)です。 マップを構築するときにストアド デリゲート オブジェクトを指定することができます。デリゲート オブジェクトを指定しないと、既定値が比較`operator<(key_type, key_type)`です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`です。  
  
 このようなデリゲート オブジェクト必要があります、厳密弱順序強制型のキーで[map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `key_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`key_comp()(X, Y)`が true の場合、 `key_comp()(Y, X)` false である必要があります。  
  
 場合`key_comp()(X, Y)`が true の場合、`X`をする前に並べ替えるといいます`Y`です。  
  
 場合`!key_comp()(X, Y) && !key_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 任意の要素に対して`X`の直前まで`Y`、被制御シーケンスの`key_comp()(Y, X)`は false。 (既定のデリゲート オブジェクトのキーしない値が減少します。)テンプレート クラスとは異なり[マップ](../dotnet/map-stl-clr.md)、テンプレート クラスのオブジェクト`map`すべての要素のキーが一意であることは不要です。 (2 つまたは複数のキーが持てると同じ順序です。)  
  
 各要素には、個別のキーと、マップされた値が含まれています。 シーケンスは、シーケンス (対数時間) の検索、挿入、削除、任意の要素数の要素の数の対数に比例して操作できるような方法で表されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 マップは、被制御シーケンス内の要素を指定する反復子を指定する、隣接する要素をステップ実行できますが、双方向反復子をサポートします。 特殊なヘッド ノードによって返される反復子に対応[map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達するマップの反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定されたマップ要素を参照することはできないことに注意してください。  
  
 マップの反復子は、それに関連付けられているコンテナーへのハンドルを格納する関連付けられているマップ ノードへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 マップの反復子は、関連付けられているマップ ノードにいくつかのマップに関連付けられている限り有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [マップ](../dotnet/map-stl-clr.md)   
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)