---
title: multimap (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- <cliext/map> header [STL/CLR]
- multimap class [STL/CLR]
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 168c6afec0f8f195d1315a54eff2794f7e3fd07e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="multimap-stlclr"></a>multimap (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`multimap`1 つの要素を格納する各ノードのバランスの取れた (ほとんど) の順序付けられたツリーとして要素のシーケンスを管理します。 要素は、シーケンスとよいに沿って移動する、マップされた値は、管理するためのキーで構成されます。  
  
 下記に、`GValue`と同じです。  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 それぞれの文字について以下に説明します。  
  
 `GKey` 同じ`Key`ref 型を後者には、しない限り、どのケースでは `Key^`  
  
 `GMapped` 同じ`Mapped`ref 型を後者には、しない限り、どのケースでは `Mapped^`  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
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
|[multimap::const_iterator (STL/CLR)](../dotnet/multimap-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[multimap::const_reference (STL/CLR)](../dotnet/multimap-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[multimap::const_reverse_iterator (STL/CLR)](../dotnet/multimap-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[multimap::difference_type (STL/CLR)](../dotnet/multimap-difference-type-stl-clr.md)|2 つの要素間の距離を (場合によっては符号付き) の型。|  
|[multimap::generic_container (STL/CLR)](../dotnet/multimap-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[multimap::generic_iterator (STL/CLR)](../dotnet/multimap-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[multimap::generic_reverse_iterator (STL/CLR)](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[multimap::generic_value (STL/CLR)](../dotnet/multimap-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[multimap::iterator (STL/CLR)](../dotnet/multimap-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[multimap::key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)|2 つのキーの順序付けのデリゲート。|  
|[multimap::key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)|順序付けキーの型です。|  
|[multimap::mapped_type (STL/CLR)](../dotnet/multimap-mapped-type-stl-clr.md)|各キーに関連付けられているマップされた値の型。|  
|[multimap::reference (STL/CLR)](../dotnet/multimap-reference-stl-clr.md)|要素への参照の型です。|  
|[multimap::reverse_iterator (STL/CLR)](../dotnet/multimap-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[multimap::size_type (STL/CLR)](../dotnet/multimap-size-type-stl-clr.md)|(負符号) 距離は 2 つの要素の型。|  
|[multimap::value_compare (STL/CLR)](../dotnet/multimap-value-compare-stl-clr.md)|2 つの要素値の順序付けのデリゲート。|  
|[multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[multimap::begin (STL/CLR)](../dotnet/multimap-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[multimap::clear (STL/CLR)](../dotnet/multimap-clear-stl-clr.md)|すべての要素を削除します。|  
|[multimap::count (STL/CLR)](../dotnet/multimap-count-stl-clr.md)|指定したキーに一致する要素の数をカウントします。|  
|[multimap::empty (STL/CLR)](../dotnet/multimap-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[multimap::equal_range (STL/CLR)](../dotnet/multimap-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[multimap::erase (STL/CLR)](../dotnet/multimap-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[multimap::find (STL/CLR)](../dotnet/multimap-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[multimap::insert (STL/CLR)](../dotnet/multimap-insert-stl-clr.md)|要素を追加します。|  
|[multimap::key_comp (STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)|2 つのキーの順序付けのデリゲートをコピーします。|  
|[multimap::lower_bound (STL/CLR)](../dotnet/multimap-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検出します。|  
|[multimap::make_value (STL/CLR)](../dotnet/multimap-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[multimap::multimap (STL/CLR)](../dotnet/multimap-multimap-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[multimap::rbegin (STL/CLR)](../dotnet/multimap-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[multimap::rend (STL/CLR)](../dotnet/multimap-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[multimap::size (STL/CLR)](../dotnet/multimap-size-stl-clr.md)|要素の数をカウントします。|  
|[multimap::swap (STL/CLR)](../dotnet/multimap-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[multimap::to_array (STL/CLR)](../dotnet/multimap-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[multimap::upper_bound (STL/CLR)](../dotnet/multimap-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[multimap::value_comp (STL/CLR)](../dotnet/multimap-value-comp-stl-clr.md)|2 つの要素値の順序付けのデリゲートをコピーします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[multimap::operator= (STL/CLR)](../dotnet/multimap-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator!= (multimap) (STL/CLR)](../dotnet/operator-inequality-multimap-stl-clr.md)|かどうかを`multimap`オブジェクトが他と等しくない`multimap`オブジェクト。|  
|[operator< (multimap) (STL/CLR)](../dotnet/operator-less-than-multimap-stl-clr.md)|かどうかを`multimap`オブジェクトが他よりも小さい`multimap`オブジェクト。|  
|[operator<= (multimap) (STL/CLR)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|かどうかを`multimap`オブジェクトが別に小さい`multimap`オブジェクト。|  
|[operator== (multimap) (STL/CLR)](../dotnet/operator-equality-multimap-stl-clr.md)|かどうかを`multimap`オブジェクトが他と等しい`multimap`オブジェクト。|  
|[operator> (multimap) (STL/CLR)](../dotnet/operator-greater-than-multimap-stl-clr.md)|かどうかを`multimap`オブジェクトが他よりも大きい`multimap`オブジェクト。|  
|[operator>= (multimap) (STL/CLR)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)|かどうかを`multimap`オブジェクトがより大きいか等しい間`multimap`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|ITree\<キー、値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、個々 のノードとして、制御するシーケンスの記憶域を解放します。 順序付けられた 1 つのノードの内容を別にコピーからではなく、ノード間のリンクを変更することにより保持される (ほとんど) バランスの良いツリーに要素を挿入します。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。  
  
 オブジェクトがストアド デリゲート型のオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます[multimap::key_compare (STL/CLR)](../dotnet/multimap-key-compare-stl-clr.md)です。 Multimap を構築するときにストアド デリゲート オブジェクトを指定することができますデリゲート オブジェクトを指定しないと、既定値が比較`operator<(key_type, key_type)`です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[multimap::key_comp (STL/CLR)](../dotnet/multimap-key-comp-stl-clr.md)`()`です。  
  
 このようなデリゲート オブジェクト必要があります、厳密弱順序強制型のキーで[multimap::key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `key_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`key_comp()(X, Y)`が true の場合、 `key_comp()(Y, X)` false である必要があります。  
  
 場合`key_comp()(X, Y)`が true の場合、`X`をする前に並べ替えるといいます`Y`です。  
  
 場合`!key_comp()(X, Y) && !key_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 任意の要素に対して`X`の直前まで`Y`、被制御シーケンスの`key_comp()(Y, X)`は false。 (既定のデリゲート オブジェクトのキーしない値が減少します。)テンプレート クラスとは異なり[マップ (STL/CLR)](../dotnet/map-stl-clr.md)、テンプレート クラスのオブジェクト`multimap`すべての要素のキーが一意であることは不要です。 (2 つまたは複数のキーが持てると同じ順序です。)  
  
 各要素には、個別のキーと、マップされた値が含まれています。 シーケンスは、シーケンス (対数時間) の検索、挿入、削除、任意の要素数の要素の数の対数に比例して操作できるような方法で表されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 Multimap は、被制御シーケンス内の要素を指定する反復子を指定する、隣接する要素をステップ実行できますが、双方向反復子をサポートします。 特殊なヘッド ノードによって返される反復子に対応[multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達する multimap の反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定 multimap の要素を参照できないことに注意してください。  
  
 Multimap の反復子は、そのノードに関連付けられた multimap、さらに関連付けられているコンテナーへのハンドルを格納するへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 その multimap ノードに関連付けられたはいくつかの multimap に関連付けられていれば、multimap の反復子は有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)